## *自上而下介绍*
建立一个最大文件A 然后在A里面第一需要建立的是整个基准，后续不断的插入空的Bi文件， 把需要的Bi空文件建完以后，根据顶层的基准创建B1的功能，完善B1以后 后面的零件可以根据B1，也可以根据顶层的基准来完成自身的创建。以此类推，直到完成整个A的建立。

## *洗衣机算法伪代码*


water_in_switch（open）
while (water_volumw ！= setting_water_volume)
    get_water_volume（）
water_in_switch（close）

while(time_counter（）!= setting_time )
    motor_run（left）
    motor_run（right）
halt（returncode）

water_out_switch（open）
while (water_volumw != 0 )
    get_water_volume（）
water_out_switch（close）
IF halt（returncode）
    RETURN success
ELSE  
    return false


