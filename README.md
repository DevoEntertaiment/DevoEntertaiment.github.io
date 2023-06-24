<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <link rel="stylesheet" href="inline.css">
    <title>Моя перша гра на Pyton</title>
    <link rel="icon" href="img/Starwars.png"/>
</head>
<body>

    <div class="main">
        <h1>Розробка гри WOS - World Of Spaceships</h1>

        <div class="page">
            <p>
                Hello world! Тут я розробив свою гру на пітоні, але зараз я займаюся розробкою сайтів. 
                Якщо ви це читаєте, значить вам стало цікаво, чого я досяг і що вийшло в кінці. 
                Ця робота для мене була дуже складною, але ви можете самі спробувати собі у програмуванні, 
                адже це набагато цікавіше ніж сидіти та грати в інші ігри.
            </p>
            <p>
                Одже, далі я покажу етапи створення гри, та для зручності перегляду, я розмістив їх у вкладках. Для цього довелося значно прокачати мої знання з вебу.
            </p>
            <p>Одже, помчали: </p>
        </div>
        <div class="tabs">
            <div class="tab">
             <input type="radio" id="tab1" name="tab-group" checked>
             <label for="tab1" class="tab-title">Етап 1</label> 
             <section class="tab-content"><div class="page">
                <p>
                    <img class="right" src="img/WOS-gif.gif" alt="">
                    На початку створення гри, необхідно створити поле для гравця та інших елементів гри.
                     Для цього я поставив висоту та ширину поля за допомогою параметрів WIDTH та HEIGHT, а також кадри за секунду FPS. 60 – я вважаю ідеальне значення.
                     Для створення гравця (тобто player), я створив спеціальний клас, де буде заданий сам персонаж та його характеристики чи здібності. До речі, не забуваємо додати спрайт гравця. Це важливо!
                     Після цього потрібно показати спрайт, щоб переконатися, що він відображається на екрані. <a href="https://drive.google.com/file/d/1llGFwe_kPKd9hw-pin9pMeRyFEgv6tiV/view?usp=sharing" target="_blank"><i>Код.</i> </a>
                </p>
            </div><div class="page">
                <p>
                    <img class="left" src="img/2 часть.gif" alt="">
                    Рух/управління. Щоб гравець рухався при натисканні кнопок Вліво або Вправо, потрібно задати ці кнопки.
                     Я встановив швидкість спрайту за замовчуванням на значення 0, крім випадків, коли натискаються кнопки Вліво або Вправо. В результаті рух більш плавний, а код простіше.
                     Цей код встановлює швидкість speedx на значенні 0 для кожного кадру, а потім перевіряє, чи не натиснута кнопка pygame.key.get_pressed() повертає словник з усіма клавішами клавіатури та значеннями True або False, які вказують на те, чи натиснута якась із них. Якщо одна з кнопок натискається, швидкість змінюється відповідно.
                     Тепер потрібно задати, щоб гравець був у межах екрану і не виходив за його межі. Для цього я додав цей код update() гравця. <a href="https://drive.google.com/file/d/17ddSmoOqRjcdETAe9ov5TYaKthVjpU-J/view?usp=drive_link" target="_blank"><i>Код.</i> </a>
                </p>
            </div></section>
            </div> 
            <div class="tab">
             <input type="radio" id="tab2" name="tab-group">
             <label for="tab2" class="tab-title">Етап 2</label> 
             <section class="tab-content"><div class="page">
                <p>
                    <img class="right" src="img/3 часть.gif"  alt="">
                    Тепер можна додати мобів (ворогів), в цьому випадку я додав ворогів метеоритів. Ось код цих ворогів. Але, є правда, метеорити не повинні виникати з нізвідки і не відлітати в нікуди. Тому я поставив y більше 0, а значення х у межах екрана. Тепер поява ворогів багато, тому я створив групу mods. Вийшов потік мобів, які опускаються вниз екраном. Але, моби рухаються рівно вниз і це нудно. Додав рух по координаті х, а також я змінив інструкцію if, яка сповнить мобів, коли ті пропадають. Залишилося зробити зіткнення та стрілянину. Стрілянину персонажа зробити легко, а ось зі зіткненнями потрібно заморочитися. Для цього, я зробив рамку навколо персонажа за допомогою ПООП (паралельний осям, що обмежує паралелепіпед). Після, у перевірці, я поставив параметр hits. З його допомогою можна перевірити, чи не вдарив моб гравця.
                    Стрілянина. Це спрайт, який з'являється в момент пострілу над спрайтом гравця і рухається з великою швидкістю. Для цього я зробив новий клас Bullet. Також я додав кнопку пропуск для пострілів куль і новий клас shoot. Зіткнення куль. Щоб мочити моби як мух, я додав ще одну перевірку, чи зачепила куля моба. Без перевірки, моби будуть як у матриці -_(о-о)_-. Якщо просто вбивати мобів, то виникне проблема: вони закінчаться. Тому потрібно просто проходити циклом по hits і для кожного знищеного мобу створювати один новий. Ось тепер це схоже на стрілянину. <a href="https://drive.google.com/file/d/1w3Juqg4xT4tnC-typ3WpWdAAdhQy8mUK/view?usp=drive_link" target="_blank">Код.</a>
                </p>
            </div>
            <div class="page ex">
                <p>
                    <img class="left" src="img/4-часть.gif" alt="">
                    Графіка. Для того, щоб моя гра не була схожа на піксельну гру, мені потрібно було додати графіку. А саме космічний корабель, кулі, метеорити і обов'язково заднє тло. Для завантаження заднього фону я використав параметр background, а для персонажа та мобів image. Також я підредагував розвірку гравця (він був занадто великий). Також точно і для метеоритів та куль. Готово! <a href="https://drive.google.com/file/d/1PyNlHUuLWthaDsTWCEGJbwhTdXP9xwkm/view?usp=drive_link" target="_blank">Код.</a>
                </p>
            </div></section>
            </div>
            <div class="tab">
             <input type="radio" id="tab3" name="tab-group">
             <label for="tab3" class="tab-title">Етап 3</label> 
             <section class="tab-content"><div class="page ex">
                <img class="right" src="img/5-часть.gif" alt="">
            <p>
                Зараз же треба заморочитися зі зіткненнями. Тому що з'явилася і нова проблема: гра почала зараховувати зіткнення навіть тоді, коли візуально їх не видно. Для цього я зробив новий спрайт зіткнень, коло це ідеальна фігура для зіткнень спрайтів. Для себе я зробив заповнення кола червоним, щоб краще бачити зіткнення спрайтів. <a href="https://drive.google.com/file/d/15I2R8JwB5a6YaAsglZp8CAmCSvDSQxUF/view?usp=drive_link" target="_blank">Код</a>
                
            </p>
        </div>
        <div class="page ex">
            <img class="left" src="img/6 часть.gif" alt="">
            <p>
                Анімація, розваги. Впадають у вічі метеорити, вони однакові і немає руйнування самих метеоритів. Для початку я додав обертання цих спрайтів за допомогою параметра "rot", а також додав випадкові розміри цих астероїдів (що більше астероїд - тим менший момент, що крутить). <a href="https://drive.google.com/file/d/1T97OMWawQewsq-QCqwfanGSJkbSZKN6y/view?usp=drive_link" target="_blank" >Код.</a>   
            </p>
        </div></section> 
            </div>
            <div class="tab">
             <input type="radio" id="tab4" name="tab-group" >
             <label for="tab4" class="tab-title">Етап 4</label> 
             <section class="tab-content"><div class="page ex">
                <img class="right" src="img/7 часть.gif" alt="">
                <p>
                    У всіх стрілялках є шкала здоров'я, броні тощо. Тому і свою гру я додав рахунок, а також функцію, яка додає очки залежно від розміру астероїду.
                    Щоб був якийсь рендеринг тексту я додав згладжування, 'anti-alised' - найкращий шрифт. Воно розмиває текст, що у маленькому розмірі букви видно згладжено. І не забуваємо вивести текст (у нашому випадку рахунок) на екран. <a href="https://drive.google.com/file/d/1WyDma2wbuMW2Npk8uFvCjbbm5yqa5xTK/view?usp=drive_link" target="_blank">Код</a>
                </p>
            </div>
            <div class="page ex">
                <img class="left" src="img/8 часть.gif" alt="">
                <p>
                    Саундтреки для гри. Музика у грі – найефективніший спосіб додати до гри «енергії». Тому, ось посилання на ефекти та музику з моєї гри: <a href="https://drive.google.com/drive/folders/1_CfJieWi5e0ZqzeAvfxtgTeMQehYn6uJ?usp=drive_link">Music</a>. І завантажуємо файл із музикою та саунтреками. <a href="https://drive.google.com/file/d/1RZ-Il3g7UkUr81inJwWsjI2KsaFU08ag/view?usp=drive_link" target="_blank">Код</a>
                </p>
            </div></section>
            </div> 
            <div class="tab">
             <input type="radio" id="tab5" name="tab-group" >
             <label for="tab5" class="tab-title">Етап 5</label> 
             <section class="tab-content"><div class="page ex">
                <img class="right" src="img/9 часть.gif" alt="">
                <p>
                    Як може існувати гра без шкали здоров'я та броні. Ось і в моїй грі має бути шкала. Тепер щоразу, коли астероїд потраплятиме в гравця, можна забирати певний рівень здоров'я. Коли рівень впаде до 0, гра закінчується. Щоб було цікавіше, я зробив, щоб великі астероїди завдавали більше шкоди. Для цього я використав властивість radius астероїду. Для смужки здоров'я створив дисплей, але замість показу просто цифр вивів смужку, якою буде видно, наскільки вона заповнена. <a href="https://drive.google.com/file/d/1GfyePpJ1hB9LJhl56LI7QgdoksflpUNO/view?usp=drive_link" target="_blank">Код.</a>
                </p>
            </div>
            <div class="page ex">
                <img class="left" src="img/10 часть.gif" alt="">
                <p>
                    Вибухи. Спочатку потрібно завантажити графіку у гру та додати її до списку. Як і у випадку зі спрайтом гравця, необхідно змінити розмір цих зображень, зробивши дві версії. Велика відтворюватиметься у місці підриву астероїда гравцем, а маленька там, де астероїд врізається в корабель гравця. Далі потрібно створити спрайт, що є вибухом на екрані. Зображення спрайту швидко змінюватиметься, переходячи від одного зображення до іншого в наборі. Діставшись останнього, спрайт зникне. <a href="https://drive.google.com/file/d/1E86phWmV5u1D4DUv0EGUoCV5-83K4sSB/view?usp=drive_link" target="_blank">Код.</a>
                </p>
            </div></section>
            </div>
            <div class="tab">
             <input type="radio" id="tab6" name="tab-group" >
             <label for="tab6" class="tab-title">Етап 6</label> 
             <section class="tab-content"><div class="page ex">
                <img class="right" src="img/11 часть.gif" alt="">
                <p>
                    Життя гравця. Коли гравець закінчує життя, гравець просто зникає. Для вирішення цієї проблеми я додав анімацію вибуху та звук програшу. Далі я додав кілька життів гравцю. Їх можна відстежувати за допомогою змінної, але також потрібно виводити їх на екран. Замість чисел можна використовувати мініатюрні зображення корабля гравця. Тепер, у разі смерті гравця, замість. <a href="https://drive.google.com/file/d/1owyKfnV7YwS2UAF40ClmWXlEGjbtVZvJ/view?usp=drive_link" target="_blank">Код.</a>
                </p>
            </div>
            <div class="page">
                <img class="left" src="img/12 часть.gif" alt="">
                <p>
                    Поліпшення. У моєму шутері вже багато чого, але чогось важливого не вистачає — можливості для гравця робити свій корабель сильнішим. Для цього я додав 2 можливих покращень, здоров'я та зброю. Здоров'я відновлюватиме здоров'я гравця, зброя збільшує вогневу міць. Для початку потрібно додати ще один спрайт, який буде об'єктом поліпшення. Щоб спростити цей процес, можна скопіювати клас Bullet() та додати пару змін. Це спрацює, тому що їхня поведінка дуже схожа: з'явитися в певному місці (місці астероїда, який був знищений) і рухатися вниз, а потім прибрати спрайт, якщо він піде за межі екрана. При відображенні поліпшення випадково вибиратимемо між «здоров'ям» і «зброєю». Тепер я додав ще одну перевірку зіткнень. Спочатку обробляється покращення здоров'я, яке повертає гравцеві випадкове значення здоров'я. Зі «зброєю» дещо складніше, тому йому буде присвячений наступний матеріал. <a href="https://drive.google.com/file/d/1aiiuGHu-xYd_TLNZsMzZ1sIkMxmKFv41/view?usp=drive_link" target="_blank">Код.</a>
                </p>
            </div></section>
            </div>
            <div class="tab">
             <input type="radio" id="tab7" name="tab-group" >
             <label for="tab7" class="tab-title">Етап 7</label> 
             <section class="tab-content"><div class="page ex">
                <img class="right" src="img/13 часть.gif" alt="">
                <p>
                    Поліпшення (2 частина). Зараз потрібно приділити ще трохи уваги. Спершу я додав нові властивості в спрайт Player: power відстежуватиме «рівень сили» (з кожним пострілом, що збільшується з кожним пострілом), а power_time — знижувати його через деякий час. Ще я додав звуки в ті моменти, коли гравець підбирає спрайти покращень. Після цього потрібно просто запускати їх під час зіткнення гравця з відповідним покращенням. <a href="https://drive.google.com/file/d/1c9FOjM_r5Vl8K3O4-9j7nat66e3viuZr/view?usp=drive_link">Код.</a>
                </p>
            </div>
            <div class="page">
                <img class="left" src="img/14 часть.gif" alt="">
                <p>
                    Гра закінчена. Зараз, якщо гравець закінчує життя, програма просто різко обривається. Виглядає не дуже приємно, тому додамо екран «Гра закінчена» і дамо можливість гравцям розпочати спочатку, якщо вони хочуть. Причина зупинення програми в тому, що ігровий цикл управляється змінною running (значення якої може бути тільки True або False), і в момент смерті гравця він стає False. Натомість зробимо так, щоб відслідковувався стан гри (state). Також потрібно додати екран початку або закінчення гри, де можна вибрати при старті почати і наприкінці гри – почати спочатку. Залишилося зробити клавіші для початку гри та виходу з неї. Також я додав нахил персонажа при натисканні кнопок ліворуч і праворуч. <a href="https://drive.google.com/file/d/1Aop-Rh9seAQMnqOuyWjK9O8Z2AJdkVhk/view?usp=drive_link">Код.</a>
                </p>
            </div></section>
            </div>   
        </div>    
  </div>    

</body>
</html>
 
