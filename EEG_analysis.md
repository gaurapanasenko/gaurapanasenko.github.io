<style>
	.reveal {
		font-size: 1.75em
	}
</style>

Дисертаційна робота за темою:

#### Дослідження динаміки психофізіологічних станів мозку людини, які ідентифікують її розслаблення та концентрацію, за допомогою електроенцефалограм.

Керівник: Білозьоров В. Е.

---

#### Задачі дослідження
1. Перевірка валідності та обробка даних у режимі реального часу, включаючи розгляд сценаріїв часткової відсутності даних.
2. Розробка та впровадження методів обробки та фільтрації артефактів при зборі ЕЕГ-даних за допомогою фільтрів.
3. Використання методів нелінійної динаміки для аналізу поведінки хаотичних часових рядів ЕЕГ-даних у випадку розслаблення та концентрації.
4. Розробка системи, яка на основі часових рядів ЕЕГ-даних, здатна обчислювати рівень розслаблення та концентрації мозку.

---

#### Актуальність теми

У сучасному світі існують доступні пристрої для отримання ЕЕГ даних у режимі реального часу, але існує недостатньо розроблених та оптимізованих підходів до аналізу цих даних та реалізації відповідних алгоритмів. Це ставить перед дослідниками та розробниками питання щодо того, як ефективно обробляти дані ЕЕГ в залежності від конкретної задачі. Однією з ключових областей дослідження у цьому контексті є визначення психофізіологічних станів мозку, зокрема, розслаблення та концентрації. Розуміння та краще використання цих станів мають важливе значення для подальшого розвитку застосувань ЕЕГ-технологій у медицині, психології, спорті, освіті та інших сферах людської діяльності.

---

#### Біофізична модель

![[Pasted image 20240402203352.png]]

---

![[EEG_10-10_system_with_additional_information.svg|1000]]

---

![[Pasted image 20240402204920.png|1000]]

---

#### Пристрої зчитування ЕЕГ - Медичні

![[Pasted image 20240402205938.png]]

---

#### Пристрої зчитування ЕЕГ - Muse 2

![[Pasted image 20240402210018.png|900]]

---

#### Математичні моделі

* Рекурентний аналіз - це метод дослідження динамічних систем, що базується на вивченні їхньої поведінки через час шляхом ітераційного застосування математичних виразів. Цей аналіз дозволяє виявити структуру та властивості системи, зокрема, визначити стабільність, кінцеві точки та хаотичність.
* Частотний аналіз - це метод дослідження сигналів та систем, що використовується для вивчення їхньої структури та властивостей у частотному діапазоні. Це дозволяє виявити основні складові сигналу та їхні амплітуди. Частотний аналіз допомагає в розумінні динаміки сигналів, виявленні паттернів та залежностей між ними, а також у розробці методів фільтрації та обробки сигналів для подальшого використання в різних додатках.

---

#### Рекурентні діаграми

![[RQA_diagrams.png]]


---

#### Рекурентні параметри

- Determinism (DET) - Детермінізм

	$\displaystyle\text{DET} = \frac{\sum_{\ell=\ell_\min}^N \ell\, P(\ell)}{\sum_{\ell=1}^{N}\ell P(\ell)}$, де $P(\ell)$ - це частотний розподіл довжин $\ell$ діагональних ліній (тобто він враховує, скільки екземплярів мають довжину $\ell$)
- Average diagonal line length (L) - Середня довжина діагональної лінії

	$\displaystyle\text{L} = \frac{\sum_{\ell=\ell_\min}^N \ell\, P(\ell)}{\sum_{\ell=\ell_\min}^N P(\ell)}$
	
- Trapping time (TT) - Час попадання в пастку

	$\displaystyle\text{TT} = \frac{\sum_{v=v_\min}^{N} v P(v)} {\sum_{v=v_\min}^{N} P(v)}$,	де $P(v)$ - це частотний розподіл довжин $v$ вертикальних ліній, які мають принаймні довжину $v_\min$. 

---

#### Частотний аналіз та ритми мозку

![[Welch_demo.png]]

---

#### Перетворення Фур'є

Перетворення Фур'є функції $f(t)$ математично визначається як комплекснозначна функція $ F(\omega) \,$, яка задається інтегралом:

$ \displaystyle F(\omega) = \int_{-\infty}^\infty f(t) e^{-i\omega t} dt  $

'''Обернене перетворення''' Фур'є задається виразом:

$$ \displaystyle \dfrac{1}{2\pi}\int_{-\infty}^\infty F(\omega) e^{i\omega t} d\omega = f(t) $$

---

#### Ритми мозку

|Ритм|Діапазон (Гц)|Опис|
|---|---|---|
|Дельта|0.5 - 4|Глибокий сон або безсвідомість|
|Тета|4 - 8|Релаксація, медитація, зосередженість|
|Альфа|8 - 13|Спокій, релаксація при закритих очах|
|Бета|13 - 30|Бодрість, концентрація, висока активність мозку||   |
|Гама|30 - 100|Висока концентрація, когнітивні процеси, увага|

---

#### Частотні шуми

|Тип шуму|Діапазон (Гц)|Опис|
|---|---|---|
|Низькочастотний шум (LFN)|0.1 - 1|Шум з низькою частотою, може бути пов'язаний з рухами м'язів або серцевими артефактами|
|Високочастотний шум (HFN)|> 30|Шум з високою частотою, може виникати внаслідок електричної активності шкіри або електромагнітних джерел|
|Інтерференція мережі|50/60|Шум, що виникає внаслідок інтерференції від електричної мережі|
|Рухові артефакти|Дельта - Бета|Артефакти, спричинені рухами пацієнта|
|Біологічні артефакти|-|Артефакти, пов'язані з проводимістю шкіри, рухами очей або м'язів обличчя|

---

#### Ритми мозку декількох сигналів

![[Band_waves.png]]

---

#### Альфа канал, як показник розлаблення при закритих очах

![[Alpha_power.png]]

---

#### Аналіз незалежних компонент

![[ICA_demo.png]]

---

# Дякую за увагу!