# hh-school-search
## Дз по поиску 

Реализовать свой простой поиск на java, который может работать в 2 режимах: 

1. Индексация: на вход подаётся название файла(директории) индекса и исходный файл, где каждая строка является отдельным документом в индексе, и происходит построение индекса, который записывается в файл(директорию). 
2. Поиск: на вход подаётся название файла индекса и запрос, на выходе получаем список документов подходящих под этот запрос.

Начать можно с написания наивной реализации инвертированного индекса и запросов по одному слову. В итоге должна получиться jar-ка, которая может работать в 2 режимах. Сдавать в виде PR к этому репозиторию с инструкцией для сборки и запуска, и списком что было реализованно. 

## Доп. задания (не обязательно, в порядке усложнения): 
* написать реализацию запросов AND и NOT
* написать реализацию фразовых запросов
* применить оптимизации при построении индекса из лекции
* написать реализацию OR с задаваемым минимальным количеством вхождений (пример: есть запрос java OR scala OR kotlin, мы хотим все документы где есть минимум 2 слова)

## Срок сдачи

31.01.2019 23:59

# Инструкция для сборки и запуска
1. Открыть командную строку или Git Bash **от имени администратора**
2. Перейти в каталог проекта (<путь_на_диске_к_этому_локальному_репозиторию>/search/)
3. Собрать проект командой `mvn compile package`
4. Перейти в каталог target командой `cd target` из текущей директории
5. Запустить программу в одном из двух возможных режимов:
    3.1. **Режим индексации** запускается по команде `java -jar hh-search-1.0-SNAPSHOT.jar INDEX path-to-index-file path-to-source-file` (где path-to-index-file - путь к файлу индекса
    path-to-source-file - путь к файлу, из которого берутся строки (aka документы)
    на данный момент программа *поддерживает только работу с текстовыми файлами, файлы должны быть предварительно созданы*)
    **На выходе** в файл, находящийся по адресу path-to-index-file записываются все термы (слова) из исходного документа и каждому терму в соответствие ставится список документов, в которых встречается данный терм
    3.2. **Режим поиска** запускается по команде `java -jar hh-search-1.0-SNAPSHOT.jar SEARCH path-to-index-file search-query` (где 
    path-to-index-file - путь к файлу индекса
    search-query - поисковый запрос (на данный момент поддерживается только поиск по одному слову)
    на данный момент программа *поддерживает только работу с текстовыми файлами, файлы должны быть предварительно созданы*)
    **На выходе** в консоли отображается список документов, в которых встречалось искомое слово
6. Соотнести полученный результат, с тем что указано в пп. 3.1 или 3.2 в строке **на выходе**.

# Что реализовано на данный момент?
* Базовый режим работы программы, поддерживающий поиск по одному слову
=======
