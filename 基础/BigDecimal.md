#### 1使用String类型的BigDecimal不会丢失精度，使用其他类型的BigDecimal会丢失精度

```
        BigDecimal a = new BigDecimal(1.01);
        BigDecimal b = new BigDecimal(1.02);
        BigDecimal c = new BigDecimal("1.01");
        BigDecimal d = new BigDecimal("1.02");
        System.out.println(a.add(b));
        // 结果 2.0300000000000000266453525910037569701671600341796875
        System.out.println(c.add(d));
        // 结果 2.03
```
#### 2除法要保留精度和位数，否则可能会报错

```
BigDecimal a = new BigDecimal("5.4");
        BigDecimal b = new BigDecimal("3.1");
        // 除法要保留精度和位数，否则可能会报错
        // System.out.println(a.divide(b));
        System.out.println(a.divide(b,3, RoundingMode.HALF_UP));
```
