### Прут Тетяна ІПЗ 4.02
## Реалізація перетворень між системами координат

## Мета роботи
Ознайомитися з різними системами координат (декартовою, полярною та сферичною) та отримати практичні навички у переході між ними. Визначити обчислювальну ефективність розрахунку відстаней у цих системах координат через бенчмаркінг.

## Завдання 
### 1. Перехід між системами координат:

  ##### Двовимірний простір: Декартова та полярна системи координат   
Перетворення між полярними та декартовими координатами виконувалося за наступними формулами:
  *З полярної у декартову:*
  𝑥 = 𝑟 ⋅ cos(𝜃)
  y = r ⋅ sin(θ)

  *З декартової у полярну:*
  r = Math.sqrt(x * x + y * y)
  theta = Math.atan2(y, x)

Результати перетворень перевірялися зворотним переходом і порівнянням початкових та отриманих значень. Всі розрахунки були коректними. 

  ##### Тривимірний простір: Декартова та сферична системи координат
Перетворення між сферичними та декартовими координатами виконувалося за такими формулами:
  *З сферичної у декартову:*
  x = r * Math.sin(phi) * Math.cos(theta);
  y = r * Math.sin(phi) * Math.sin(theta);
  z = r * Math.cos(phi);

  *З декартової у сферичну:* 
  r = Math.sqrt(x * x + y * y + z * z);
  theta = Math.atan2(y, x);
  phi = Math.acos(z / r);
​
Як і у випадку з полярними координатами, перевірка виконувалася зворотним переходом, і коректність підтверджувалася. 

### 2. Розрахунок відстаней у сферичній системі координат
Розрахунок відстаней у сферичній системі координат виконувалося за такими формулами:
##### 1. Через об'єм сфери:
   d =sqrt((x2−x1)^2+(y2−y1)^2+(z2−z1)^2)
##### 2. По поверхні сфери:
   d = arccos(sin(ϕ1)sin(ϕ2)+cos(ϕ1​)cos(ϕ2)cos(θ1−θ 2))


### 3. Бенчмаркінг продуктивності
Було згенеровано 1000 пар точок для кожної системи координат і виміряно час розрахунків.
##### Декартова система: обчислення прямої відстані між точками.
##### Сферична система: обчислення великої колової відстані.

### Висновки
Декартова система є найефективнішою для обчислень прямої відстані, але не підходить для моделювання відстаней на сферичних поверхнях.

Сферична система забезпечує точні результати для великої колової відстані, що актуально для глобальних навігаційних систем, однак потребує більше часу на обчислення.

Вибирати систему потрібно залежно від того, що ти хочеш виміряти і наскільки точний результат тобі потрібен.
