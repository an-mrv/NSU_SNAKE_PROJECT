# NSU_SNAKE_PROJECT
TODO:
1. разобраться с cdm8 (in progress)
2. переписать функции на ассемблер для роста змеи (in progress)
3. добавить обработку столкновений
4. добавить reset, чтоб игру можно было перезапускать не сбрасывая моделирование.
5. добавить счетчик 
6. (по желанию) добавить счетчик для рекорда
7. навести красоту в коде, спрятать все лишнее с главной страниц
-----------
### Распределение между logisim and Cdm8:
| logisim | assembler |
|---------|-----------|
|экран | движение змеи |
| управление | ? увелечение роста змеи ?|
| спаун яблок| |
| обработка столкновений| |
| счетчик | |

-----------
### Для дальнейшей докуентации и чтоб понимать как работает
##### Алгоритм движения змеи:
1. сдвинуть координаты головы в соответсвии с направлением движения
2. на экран пустить координаты головы:
	1. `x = head x`
	2. `y = head y`
	3. `value = 1`
	4. `stop = 0`
3. `stop = 1`

4. на экран пустить координаты хвоста:
	1. `x = tail x`
	2. `y = tail y`
	3. `value = 0`
	4. `stop = 0`
5. `stop = 1`
6. сдвинуть координаты хвоста в соответсвии с направлением движения

##### Адреса регистров логисим:

###### Output: 
	0xf0 - value
	0xf1 - stop
	0xf2 - head x
	0xf3 - head y
	0xf4 - tail x
	0xf5 - tail y

	0xf6 - update screen
	
###### Input:
	0xf8 - head x
	0xf9 - head y
	0xfa - tail x
	0xfb - tail y
	0xfc - apple x
	0xfd - apple y
	0xfe - direction
---------