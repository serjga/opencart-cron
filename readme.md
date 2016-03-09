# opencart-cron
Cron for Opencart 2.x

���������� ����� � Opencart 2.x ��� ������� ������������ � ����� admin.

������� ������������� � ����� admin/cron_tasks.php ��������� �������
```
$cron->call(
    "module/ocstore_badges/cron", 
    array (
        "minute" => "*", 
        "hour" => "*", 
        "day" => "*", 
        "dayofweek" => "*", 
        "dayofmonth" => "*"
    ),
	array(
		"param1" => "value1",
		"param2" => "value2",
		...
		"paramN" => "valueN"
	)
);
```

������ �������� - ���������� � ���������� �����, � ������� ���������� ����� cron() � ����� admin/controller/module/ocstore_badges.php
������ �������� - ������ ����������, ������������ ����� �������. ����� ��������� �������� [\d\\-\*,\/].
	�������� ������� ���������� ���� �� ����� ��������, �������� "1,2,5".
	��������� ����� ����� ������ ����� ����, ��������, "1-5", ��� ������������ "1,2,3,4,5".
	����� ��������� ������ ������ ��������� �����, �� ���������� ������ �������� "\*/10", ��� ����� ������������ ��������� 0, 10, 20 � �.�.
	����� ������ ����� �������� ����������� "*".
������ �������� - ������ ������������ � ����� ���������� (�� ������������ �������). 

��� ���������� ������ ������� ������� ��� ���������� � ������������ ����� (cron, crontab) ������ �������� �������� ��������� ������:
```
������ (Command): /����_��_�����_�_�����_������/admin/cron.php
������ (Minute): *
��� (Hour): *
���� (Day of month): *
����� (Month of year): *
���� ������ (Day of week): *
```

�������:
1. ������ ������� ������ 5 ����� � 0 �� 10 �����, � �����������.
```
    array (
        "minute" => "*/5", 
        "hour" => "0-10", 
        "day" => "*", 
        "dayofweek" => "7", 
        "dayofmonth" => "*"
    )
```
2. ������ ������� � �������
```
    array (
        "minute" => "0", 
        "hour" => "0", 
        "day" => "*", 
        "dayofweek" => "*", 
        "dayofmonth" => "*"
    )
```
