---
layout: default
title: Куки (Cookie)
parent: Сниппеты
nav_order: 0
---

# Куки (Cookie)

---

Установка значения cookie:

```php
$cookie = new \Bitrix\Main\Web\Cookie("CookieName", "CookieValue", time()+86400*30);
$cookie->setSpread(\Bitrix\Main\Web\Cookie::SPREAD_DOMAIN); // распространять куки на все домены
$cookie->setDomain("mydomain.ru"); // домен
$cookie->setPath("/"); // путь
$cookie->setSecure(false); // безопасное хранение cookie
$cookie->setHttpOnly(false);
\Bitrix\Main\Application::getInstance()->getContext()->getResponse()->addCookie($cookie);
```

Получение значения Cookie:

```php
$request = \Bitrix\Main\Application::getInstance()->getContext()->getRequest();

$cookieValue = $request->getCookie("CookieName");
```

<br>
