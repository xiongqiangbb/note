## 1、使用CountDownLatch模拟并发访问

```
    public static void main(String[] args) throws InterruptedException {
        int size = 20;
        ExecutorService pool = Executors.newFixedThreadPool(20);
        CountDownLatch orderlatch = new CountDownLatch(1);
        CountDownLatch answerlatch = new CountDownLatch(size);

        for (int i = 0; i < size; i++) {
            Runnable runnable = new Runnable() {
                @Override
                public void run() {
                   try {
                        orderlatch.await();
                        SingletonDemo1 instance = SingletonDemo1.getInstance();
                        System.out.println(instance);
                        answerlatch.countDown();
                    } catch (InterruptedException e) {
                        e.printStackTrace();
                    }
                }
            };
            pool.execute(runnable);
        }
        orderlatch.countDown();
        System.out.println("发布命令");
        answerlatch.await();
        System.out.println("end");
        pool.shutdown();
    }
```
