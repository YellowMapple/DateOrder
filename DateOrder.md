# DateOrder
参与秒杀活动判断
```ruby
package newpractice.domain;

import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Date;
import java.util.Scanner;

public class Main {
    public static void main(String[] args) throws ParseException {
        //判断秒杀活动是否完成订单
        Scanner sc = new Scanner(System.in);
        String startStr = "08:00:00";
        String endStr = "23:59:59";
        SimpleDateFormat sdf = new SimpleDateFormat("HH:mm:ss");
        Date startDateTime = sdf.parse(startStr);
        Date endDateTime = sdf.parse(endStr);
        long startTime = startDateTime.getTime();
        long endTime = endDateTime.getTime();
        while (sc.hasNext()) {
            String orderStr = sc.next();
            Date orderDateTime = sdf.parse(orderStr);
            long orderTime = orderDateTime.getTime();
            if (orderTime >= startTime && orderTime <= endTime) {
                System.out.println("恭喜参加秒杀活动成功");
            } else {
                System.out.println("很抱歉，参加秒杀活动失败");
            }
        }
        System.out.println("所有订单全部完成,欢迎您的下次使用");
    }
}
```
