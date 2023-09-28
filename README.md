# TFL.Lab.1

Реализация проверки завершаемости SRS
посредством построения оценки линейных операторах размерности 2 над арктическим полукольцом.

## Запуск проекта

Для запуска проекта вам потребуется [Maven](https://maven.apache.org/). Убедитесь, что Maven установлен на вашем
компьютере перед выполнением следующих шагов.

0. Можно клонировать и запустить через IDEA. Или по старинке:

1. Клонирование репозитория

```
git clone https://github.com/ArkadiyShevyrov/TFL.Lab.1
```

2. Перейдите в директорию проекта

```shell
cd TFL.Lab.1
```

3. Сборка проекта

```
mvn clean package
```

4. Запуск приложения

```shell
java -jar target/tfl-lab-1-1.0.0.jar
```

## Информация о процессе разработки
Здесь будет теория, ссылки и информация которой я пользовался для составления этой работы:

В поисках подходящей библиотеки для SMT на Java была прочитана тема
- https://stackoverflow.com/questions/60403775/how-to-setup-a-java-development-environment-for-z3
В ней предлагалось использовать зависимость:
```
<dependency>
    <groupId>com.microsoft</groupId>
    <artifactId>z3</artifactId>
    <version>4.8.7</version>
</dependency>
```
Из https://github.com/Z3Prover/z3.

Но, насколько я понял, они не опубликовали артефакт в главный сервис Maven.
Из-за чего были бы сложности с установкой.

По этой причине мной была выбрана зависимость из https://github.com/tudo-aqua/z3-turnkey
Этот проект решает проблему нетривиальной настройки Java-проекта. По факту делая её за нас.

Новой зависимостью стала:
```
<dependency>
    <groupId>tools.aqua</groupId>
    <artifactId>z3-turnkey</artifactId>
    <version>4.12.2</version>
</dependency>
```
Её maven подгружает полностью автоматически.

Используемые материалы для составления SMT файла:

* Краткий туториал по SMT Solver
  - https://www.cs.upc.edu/~erodri/webpage/cps/lab/sat/tutorial-smt-solvers-slides/slides.pdf
* Туториал по SMT Solver
  - https://www.lri.fr/~conchon/TER/2013/2/SMTLIB2.pdf