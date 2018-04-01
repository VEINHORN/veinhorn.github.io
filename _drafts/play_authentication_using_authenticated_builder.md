---
layout: single
title: "Используем AuthenticatedBuilder для аутентификации в Play Framework"
categories: scala playframework
tags: scala playframework authentication security authenticatedbuilder
---

Разрабатывая веб-приложение или REST сервис на базе [Play Framework](https://www.playframework.com) рано или поздно встает вопрос о реализации механизма аутентификации. В *Play Framework* для этих целей можно воспользоваться как стандартными возможностями (с помощью cинглтон объекта [Security](https://github.com/playframework/playframework/blob/master/framework/src/play/src/main/scala/play/api/mvc/Security.scala)), так и посредством сторонних модулей, таких как [SecureSocial](http://www.securesocial.ws), [play2-auth](https://github.com/t2v/play2-auth), [deadbolt](https://github.com/schaloner/deadbolt-2) или [play-authenticate](https://github.com/joscha/play-authenticate) (если в качестве языка используется Java).

В тех случаях когда необходимо реализовать более сложную логику аутентификации, как например аутентификация пользователей с помощью социальных сетей (Facebook, Twitter, VK, и др.) или же разграничение прав доступа в зависимости от ролей пользователей - будет лучше воспользоваться уже готовыми решениями и остановиться на одном из модулей которые перечислены выше. Но когда у вас небольшое приложение и необходимо быстро "прикрутить" несложный механизм аутентификации, а разбираться в документации к сторонним модулям нет времени - *Play Framework* готов предложить простое решение, а именно синглтон объект [Security](https://github.com/playframework/playframework/blob/master/framework/src/play/src/main/scala/play/api/mvc/Security.scala), содержащий в себе ряд абстракций, упрощающих создание секьюрных [Action'ов](https://www.playframework.com/documentation/2.6.x/ScalaActions#What-is-an-Action?).

[Security](https://github.com/playframework/playframework/blob/master/framework/src/play/src/main/scala/play/api/mvc/Security.scala) API претерпело некоторые изменения в последнее время, и по документации не всегда сходу понятно как его использовать ([#7398](https://github.com/playframework/playframework/issues/7398), [#7320](https://github.com/playframework/playframework/issues/7320)), поэтому на базе понятного и наглядного примера мы попытаемся разобраться как реализовать простой механизм аутентификации в своем *Play* приложении.

## Структуру приложения



## Асинхронное получение данных о пользователе

План статьи:

1. Небольшое введение
2. Основная часть 
3. Заключение