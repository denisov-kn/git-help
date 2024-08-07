* Сделать папку репозиторием — git init
* «Разгитить» папку, если что-то пошло не так, — rm -rf .git
* Проверить состояние репозитория — git status
* Подготовить файлы к сохранению — git add
* Выполнить коммит — git commit
* Просмотреть историю коммитов — git log
* Инициализация репозитория git init

---

## SSH
* $ ls -la .ssh/ # вывели список созданных ключей  
* $ ssh-keygen -t ed25519 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"
* $ ssh-keygen -t rsa -b 4096 -C "электронная почта, к которой привязан ваш аккаунт на GitHub"

 * ls -a ~/.ssh # проверить, что ключи действительно сгенерировались.
 
  скопировать содержимое ключа в буфер обмена:
 * $ clip < ~/.ssh/id_rsa.pub
 для ed25519:
 * $ clip < ~/.ssh/id_ed25519.pub
 
 Проверить правильность ключа с помощью следующей команды.
 * $ ssh -T git@github.com
 
 
 *Привязать удалённый репозиторий к локальному — git remote add
 $ git remote add origin git@github.com:%ИМЯ_АККАУНТА%/first-project.git 
 
 * Убедиться, что репозитории связаны, — git remote -v
 * Отправить изменения на удалённый репозиторий — git push
 
 * Клонировать репозиторий — git clone
  
  
## Синхронизация локального и удалённого репозиториев

* git remote add origin https://github.com/YandexPracticum/first-project.git (от англ. remote, «удалённый» + add, «добавить») — привяжи локальный репозиторий к удалённому с URL https://github.com/YandexPracticum/first-project.git;
* git remote -v (от англ. verbose, «подробный») — проверь, что репозитории действительно связались;
* git push -u origin main (от англ. push, «толкать») — в первый раз загрузи все коммиты из локального репозитория в удалённый с названием origin.

## Запуск Java-файлов на компьютере и работа с JAR

* скомпилировать исходный код в байт-код  
~~~
 javac -encoding UTF-8 HelloJdk.java
~~~
*  запустить файл с байт-кодом
~~~
java -Dfile.encoding=UTF-8 HelloJdk
~~~
* Чтобы не компилировать каждый класс по отдельности
~~~
javac -d bin -encoding UTF-8 *.java 
~~~
* Команда для запуска проекта
~~~
java -cp bin Practicum 
~~~


## Как работать с JAR

~~~
jar cfe <имя jar-файла> <имя стартового класса> <список файлов> 
jar cfe library.jar Practicum -C bin .
~~~

*  запустить программу
~~~
java -jar library.jar 
~~~