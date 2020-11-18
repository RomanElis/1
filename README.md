-- phpMyAdmin SQL Dump
-- version 4.9.0.1
-- https://www.phpmyadmin.net/
--
-- Структура таблицы `deposits`
--

CREATE TABLE `deposits` (
  `id` int(10) UNSIGNED NOT NULL,
  `user_id` int(11) DEFAULT '0',
  `payment_total` decimal(10,2) DEFAULT '0.00',
  `payment_method` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `payment_info` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `real_money` int(11) DEFAULT '0',
  `paid` tinyint(4) DEFAULT NULL,
  `comment` longtext COLLATE utf8mb4_unicode_ci,
  `payment_at` timestamp NULL DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Структура таблицы `migrations`
--

CREATE TABLE `migrations` (
  `id` int(10) UNSIGNED NOT NULL,
  `migration` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `batch` int(11) NOT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Дамп данных таблицы `migrations`
--

INSERT INTO `migrations` (`id`, `migration`, `batch`) VALUES
(1, '2014_10_12_000000_create_users_table', 1),
(2, '2014_10_12_100000_create_password_resets_table', 1),
(3, '2020_10_12_133211_create_pages_table', 1),
(4, '2020_10_19_102808_create_products_table', 1),
(5, '2020_10_22_095636_create_purchases_table', 1),
(6, '2020_10_22_095703_create_deposits_table', 1),
(7, '2020_10_25_174007_create_paids_table', 1);

-- --------------------------------------------------------

--
-- Структура таблицы `pages`
--

CREATE TABLE `pages` (
  `id` int(10) UNSIGNED NOT NULL,
  `slug` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `title` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `title_h1` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `meta_title` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `meta_description` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `meta_keywords` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `description` longtext COLLATE utf8mb4_unicode_ci,
  `parent_id` int(11) DEFAULT '0',
  `position` int(11) DEFAULT '0',
  `activity` tinyint(4) DEFAULT '0',
  `template_name` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `lang_id` int(11) DEFAULT '0',
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Дамп данных таблицы `pages`
--

INSERT INTO `pages` (`id`, `slug`, `title`, `title_h1`, `meta_title`, `meta_description`, `meta_keywords`, `description`, `parent_id`, `position`, `activity`, `template_name`, `lang_id`, `created_at`, `updated_at`) VALUES
(1, 'faq', 'F.A.Q.', 'F.A.Q.', NULL, NULL, NULL, '<dl class=\"faq\">\r\n<dt>Как мне произвести обмен?</dt>\r\n<dd>Данная операция производится роботом, если он ошибся, то извините</dd>\r\n<dt>Как мне произвести обмен?</dt>\r\n<dd>Данная операция производится роботом, если он ошибся, то извините</dd>\r\n<dt>Как мне произвести обмен?</dt>\r\n<dd>Данная операция производится роботом, если он ошибся, то извините</dd>\r\n<dt>Как мне произвести обмен?</dt>\r\n<dd>Данная операция производится роботом, если он ошибся, то извините</dd>\r\n<dt>Как мне произвести обмен?</dt>\r\n<dd>Данная операция производится роботом, если он ошибся, то извините</dd>\r\n<dt>Как мне произвести обмен?</dt>\r\n<dd>Данная операция производится роботом, если он ошибся, то извините</dd>\r\n</dl>', 0, 0, 1, NULL, 0, '2020-10-23 11:53:30', '2020-11-11 15:47:24'),
(2, 'support', 'Тикеты', NULL, NULL, NULL, NULL, '<p>Есть проблема с заказом? можете написать нам об этом.</p>\r\n<p>Рассписывайте максимального подробно.</p>\r\n<p>&nbsp;</p>', 0, 0, 1, 'page_support', 0, '2020-10-30 06:30:24', '2020-11-05 20:27:53'),
(3, 'contacts', 'Контактная информация', NULL, NULL, NULL, NULL, '<p style=\"text-align: center;\"><strong>ОСТЕРЕГАЙТЕСЬ МОШЕННИКОВ !! НАШИ КОНТАКТЫ ТОЛЬКО НА ЭТОЙ СТРАНИЦЕ</strong></p>\r\n<p style=\"text-align: center;\"><strong>Режим работы тех.поддержки: е</strong><strong>жедневно - с 10:00 до 24:00&nbsp;</strong><strong>по МСК</strong></p>\r\n<p style=\"text-align: center;\">&nbsp;</p>\r\n<p style=\"text-align: center;\"><strong>По вопросам консультации и замены:<br /></strong></p>\r\n<p style=\"text-align: center;\">&nbsp;</p>\r\n<p style=\"text-align: center;\">Telegram&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/telegram.png\" />&nbsp;@<a href=\"http://t.me//YOUT_NAME\">YOUT_NAME</a>&nbsp;(+канал&nbsp;<a href=\"https://t.me//YOUT_NAME\">@YOUT_NAME</a>)<br /><br />Почта&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/ticket.png\" alt=\"ТИКЕТ (Для зарегистрированных пользователей)\" />&nbsp;YOUT_NAME@yandex.ru</p>\r\n<p style=\"text-align: center;\"><a href=\"../../../support/\">Создать&nbsp;</a><a href=\"../../../support/\">Тикет</a>&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/ticket.png\" alt=\"ТИКЕТ (Для зарегистрированных пользователей)\" />&nbsp;(для зарегистрированных пользователей)</p>\r\n<p style=\"text-align: center;\">Skype&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/skype.png\" alt=\"SKYPE\" />&nbsp;<a href=\"skype:YOUT_NAME?chat\">akk-seller.online</a>&nbsp;(при добавлении проверяйте логин в личных данных)</p>\r\n<p style=\"text-align: center;\">ICQ&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/icq.png\" alt=\"ICQ\" /> 000000<br /><br /></p>\r\n<p style=\"text-align: center;\">&nbsp;</p>\r\n<p style=\"text-align: center;\"><strong>Если Вы хотите продать у нас товар - по вопросам поставок товара:<br /></strong></p>\r\n<p style=\"text-align: center;\">Telegram&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/telegram.png\" />&nbsp;<a href=\"http://t.me/YOUT_NAME\">@YOUT_NAME</a></p>\r\n<p style=\"text-align: center;\">ICQ&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/icq.png\" />&nbsp;000000</p>\r\n<p style=\"text-align: center;\">&nbsp;</p>\r\n<p style=\"text-align: center;\">Telegram&nbsp;<img style=\"vertical-align: middle;\" src=\"../../../uploads/icons/telegram.png\" /><a href=\"http://t.me/YOUT_NAME\">@YOUT_NAME</a></p>', 0, 0, 1, NULL, 0, '2020-11-05 18:22:08', '2020-11-18 05:47:17'),
(4, 'rules', 'Правила сервиса', NULL, NULL, NULL, NULL, '<p>Условия покупки, возвращения и т.д.</p>', 0, 0, 1, NULL, 0, '2020-11-09 09:29:02', '2020-11-09 09:29:02');

-- --------------------------------------------------------

--
-- Структура таблицы `paids`
--

CREATE TABLE `paids` (
  `id` int(10) UNSIGNED NOT NULL,
  `attach_id` int(11) DEFAULT '0',
  `slug` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `type` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT ''
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Дамп данных таблицы `paids`
--

INSERT INTO `paids` (`id`, `attach_id`, `slug`, `type`) VALUES
(96, 115, '1c01deab21bcb34f289242edc52b796a987a86c8', 'Purchase'),
(97, 117, 'eebb0c43daf2f9d161374599918501fa0d7ebcb0', 'Purchase'),
(99, 118, 'ae0ebbc7cbfc3d5d2ba6643650ea74a5b8a4e75f', 'Purchase'),
(100, 119, 'f1df9e7e46b3b1a395411255eae2ce480f567610', 'Purchase'),
(101, 120, '1366a1460c109eca1c67b67c952c4dffbfe23c89', 'Purchase'),
(106, 125, '37267f4310e4bfa412f965f10f6cd855335bfb99', 'Purchase'),
(108, 127, '31b602ff01934a336f74c4b21f21eabe2272b712', 'Purchase'),
(109, 128, '6cdc9baec95e432f7321b1375668ad237a870a76', 'Purchase'),
(110, 129, 'a22b6cd340b63eb8636d61fe73a6d0fd8341976f', 'Purchase'),
(111, 130, '5bd583e09c5f437b793934c9c34d46cfd08a2baf', 'Purchase'),
(112, 131, '81401e9b2d7df7dc947c2acee295ec9e40b5ba0f', 'Purchase'),
(113, 132, 'bf915a5d7e48be43ad4c800c3559b36971ed5e9c', 'Purchase'),
(114, 133, 'b0996c40ead72c965719c75fbf8effb4332b4534', 'Purchase'),
(115, 134, 'a440358d7ebd7df81c5ec2f45262235bf06cbff3', 'Purchase'),
(116, 135, 'dcc2a1f3b82d3044dbc686704b5f18de6de7eee2', 'Purchase'),
(117, 136, 'e84f96e9de3a02af30a8f195c07eebd03f43076b', 'Purchase'),
(118, 137, '421a7e3270c24730685bc30c0dbad8bbe25a5418', 'Purchase'),
(119, 138, '82ae5b782b78a66b8e5e5d6a34e347bb8f76112a', 'Purchase'),
(120, 139, '831c7c59adcf1034fb7b554068e103f22f5f216f', 'Purchase'),
(121, 140, '2325befb292d1bd0d16659e34ef8967eb3c874ec', 'Purchase'),
(122, 141, '4bb3f3b51249a4b4aa848492d2ef3fc8e7c271be', 'Purchase'),
(123, 142, '6a5c0edfb6a1bc1f4926da56b8f1ea974fb766ff', 'Purchase'),
(124, 143, '64056d48725f4099dd5396529813cb16d8eb8a88', 'Purchase'),
(125, 144, '8e8f4d05e29ae457d3276ba180d26da167f70d76', 'Purchase'),
(126, 145, 'e71ebb87a0bc950e6ba42ab316fa6e77c7abd89a', 'Purchase'),
(127, 146, 'ddde6e4cba445495b80d7ed631d5533a40a6b017', 'Purchase'),
(128, 147, '920ef82602d23edeb64a6838b5eea77b2ddb4817', 'Purchase'),
(131, 150, 'ef00cd4bb91063d3afd67f912d33e3c36b03193a', 'Purchase'),
(132, 151, '3a4d334723c842c810d9d8a6227c0b8998101e93', 'Purchase'),
(134, 153, '449fd4ff5395761a5c8fc3102a99e216133ac60b', 'Purchase'),
(135, 154, '580b3c8233b55aafcac9e57fa66cba5a0745ce35', 'Purchase'),
(136, 155, '9cb5f23bada78e1c2dd32a029ecef8f75ac711c6', 'Purchase'),
(137, 156, '6b71d6c3144def7b34aa74d246b7d4da9f816ed2', 'Purchase'),
(138, 157, 'f7b14d3f769143b63da50896371eec64eb058162', 'Purchase'),
(139, 158, '0601e608d9f89ed19a82f400fd37b0f7f5101ef8', 'Purchase'),
(140, 159, '58542e029c5df2dd5909504a0d441343c8a6f110', 'Purchase'),
(143, 162, 'e54a3dc8f753c0ce2332df75ec6db015bd890fef', 'Purchase');

-- --------------------------------------------------------

--
-- Структура таблицы `password_resets`
--

CREATE TABLE `password_resets` (
  `email` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `token` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `created_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

-- --------------------------------------------------------

--
-- Структура таблицы `products`
--

CREATE TABLE `products` (
  `id` int(10) UNSIGNED NOT NULL,
  `title` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `type` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT '',
  `image` mediumtext COLLATE utf8mb4_unicode_ci,
  `description` longtext COLLATE utf8mb4_unicode_ci,
  `price` decimal(10,2) DEFAULT '0.00',
  `goods` longtext COLLATE utf8mb4_unicode_ci,
  `stock` int(11) DEFAULT '0',
  `position` int(11) DEFAULT '0',
  `activity` tinyint(4) DEFAULT '0',
  `sales` int(11) DEFAULT '0',
  `last_sale` timestamp NULL DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Дамп данных таблицы `products`
--

INSERT INTO `products` (`id`, `title`, `type`, `image`, `description`, `price`, `goods`, `stock`, `position`, `activity`, `sales`, `last_sale`, `created_at`, `updated_at`) VALUES
(1, 'VK - РОССИЯ', 'header', '', '', '0.00', '', 0, 0, 1, 0, NULL, '2020-10-23 12:21:43', '2020-11-08 15:47:19'),
(2, 'в логине почта2', 'subheader', '', '', '0.00', '', 0, 11, 1, 0, NULL, '2020-10-23 12:22:21', '2020-11-08 15:46:40'),
(3, 'в логине телефон', 'subheader', '', '', '0.00', '', 0, 44, 1, 0, NULL, '2020-10-23 12:22:29', '2020-11-18 05:48:16'),
(4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 'googs', 'data:image/png;base64,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', '*Аккаунты реальных людей старше 18 лет, могут быть групы, голоса, приложения, фото и друзья, вход только с русских ip. Аккаунты чекаются перед выгрузкой, процент валида составляет 99% замена не производиться ни при каких обстоятельствах.', '19.52', 'rozar8ubez@mail.ru:m853Edp2	CA	[{\"domain\":\".facebook.com\",\"expirationDate\":1830365600,\"httpOnly\":true,\"name\":\"datr\",\"path\":\"/\",\"secure\":false,\"value\":\"Ho_nXm4QbUgQHpVVOH6vEO6v\"},{\"domain\":\".facebook.com\",\"expirationDate\":1830365600,\"httpOnly\":true,\"name\":\"sb\",\"path\":\"/\",\"secure\":false,\"value\":\"G4_nXgFEPx50bHh_Sn1rxsiH\"},{\"domain\":\".facebook.com\",\"expirationDate\":1830365600,\"httpOnly\":true,\"name\":\"spin\",\"path\":\"/\",\"secure\":false,\"value\":\"r.1002938672_b.trunk_t.1604764640_s.1_v.2_\"},{\"domain\":\".facebook.com\",\"expirationDate\":1830365600,\"httpOnly\":true,\"name\":\"c_user\",\"path\":\"/\",\"secure\":false,\"value\":\"100004254420660\"},{\"domain\":\".facebook.com\",\"expirationDate\":1830365600,\"httpOnly\":true,\"name\":\"fr\",\"path\":\"/\",\"secure\":false,\"value\":\"031G32LF9kh8cX7bt.AWXrpiyKWRPLXs97Ef8Vvc68uho.BffuPG.WD.F-Q.0.0.BfpdJP.AWWp_5-Mmig\"},{\"domain\":\".facebook.com\",\"expirationDate\":1830365600,\"httpOnly\":true,\"name\":\"xs\",\"path\":\"/\",\"secure\":false,\"value\":\"6%3ACtb82X-5KRn0tQ%3A2%3A1598928654%3A6408%3A13266%3A%3AAcUs2c0uDPYarOszkBTkVCrMDCkVAxBY8z0nRphLQuA\"},{\"domain\":\"\",\"expirationDate\":null}]', 1, 22, 1, 0, NULL, '2020-10-23 12:23:18', '2020-11-11 15:51:23'),
(5, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass) возраст MIX, друзей MIX', 'googs', '/uploads/products/vk.png', '<p>*VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass:Token) возраст MIX, друзей MIX</p>', '5.00', 'Login4:Pass4\r\nLogin:Pass5\r\nLogin:Pass6\r\nLogin:Pass7\r\nLogin:Pass8\r\nLogin:Pass9\r\nLogin:Pass10\r\nLogin:Pass11\r\nLogin:Pass12\r\nLogin:Pass13', 10, 66, 1, 0, NULL, '2020-10-23 12:24:41', '2020-11-09 14:12:04'),
(6, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass:Token) возраст MIX, пол Смешан, друзей 200+', 'googs', NULL, '*VK.COM (Вконтакте, ВК) - Россия (в логине:почта, номер) (от 18 до 24 лет) 100+ пол Ж СУПЕР, вручную убраны, несоответствия возраста.', '33.50', 'Login3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8\r\nLogin2:Pass2\r\nLogin3:Pass3\r\nLogin4:Pass4\r\nLogin5:Pass5\r\nLogin6:Pass6\r\nLogin7:Pass7\r\nLogin8:Pass8', 545, 33, 1, 0, NULL, '2020-10-23 12:25:56', '2020-11-18 05:48:16'),
(7, 'Тестовый товар без товар-файла', 'googs', NULL, '<p>TEXT</p>', '111.00', '', 0, 55, 1, 0, NULL, '2020-11-08 15:47:53', '2020-11-10 18:40:26');

-- --------------------------------------------------------

--
-- Структура таблицы `purchases`
--

CREATE TABLE `purchases` (
  `id` int(10) UNSIGNED NOT NULL,
  `product_id` int(11) DEFAULT '0',
  `product_title` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `user_id` int(11) DEFAULT '0',
  `user_email` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `price` decimal(10,2) DEFAULT '0.00',
  `quantity` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `payment_total` decimal(10,2) DEFAULT '0.00',
  `payment_method` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `payment_info` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `real_money` int(11) DEFAULT '0',
  `paid` tinyint(4) DEFAULT NULL,
  `goods` longtext COLLATE utf8mb4_unicode_ci,
  `comment` longtext COLLATE utf8mb4_unicode_ci,
  `payment_at` timestamp NULL DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Дамп данных таблицы `purchases`
--

INSERT INTO `purchases` (`id`, `product_id`, `product_title`, `user_id`, `user_email`, `price`, `quantity`, `payment_total`, `payment_method`, `payment_info`, `real_money`, `paid`, `goods`, `comment`, `payment_at`, `created_at`, `updated_at`) VALUES
(115, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', '', 0, 1, 'Login4:Pass4', '', '2020-11-08 14:46:32', '2020-11-08 14:46:31', '2020-11-08 14:46:32'),
(116, 7, 'Text eteette', 4, 'tester2@tester.ru', '0.00', '2', '100.00', 'balance', NULL, 0, 1, '', NULL, NULL, '2020-11-08 16:28:48', '2020-11-08 16:28:48'),
(117, 7, 'Text eteette', 4, 'tester2@tester.ru', '0.00', '2', '100.00', 'balance', NULL, 0, 1, '', NULL, NULL, '2020-11-08 16:29:19', '2020-11-08 16:29:19'),
(118, 5, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass) возраст MIX, друзей MIX', 1, 'temnik@mail.ru', '5.00', '1', '5.00', 'balance', '', 0, 1, 'Login1:Pass1', '', '2020-11-09 09:39:08', '2020-11-09 09:39:05', '2020-11-09 09:39:08'),
(119, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', '', 0, 1, 'Login5:Pass5', '', '2020-11-09 10:28:27', '2020-11-09 10:28:26', '2020-11-09 10:28:27'),
(120, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', '', 0, 1, '', '', '2020-11-09 10:29:08', '2020-11-09 10:29:06', '2020-11-09 10:29:08'),
(125, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', '', 0, 1, '', '', '2020-11-09 10:45:50', '2020-11-09 10:45:33', '2020-11-09 10:45:50'),
(127, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', '', 0, 1, '', '', '2020-11-09 11:04:16', '2020-11-09 11:04:14', '2020-11-09 11:04:16'),
(128, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', '', 0, 1, '', '', '2020-11-09 11:04:24', '2020-11-09 11:04:21', '2020-11-09 11:04:24'),
(129, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', '', 0, 1, '', '', '2020-11-09 11:13:28', '2020-11-09 11:04:35', '2020-11-09 11:13:28'),
(130, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', '', 0, 1, '', '', '2020-11-09 11:13:43', '2020-11-09 11:13:42', '2020-11-09 11:13:43'),
(131, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', '', 0, 1, '', '', '2020-11-09 11:16:32', '2020-11-09 11:16:31', '2020-11-09 11:16:32'),
(132, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара ограничено или товар закончился.', 0, 1, '', '', '2020-11-09 11:28:47', '2020-11-09 11:18:59', '2020-11-09 11:28:47'),
(133, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара стало ограничено или товар закончился в момент покупки.', 0, 1, '', '', '2020-11-09 11:31:25', '2020-11-09 11:29:32', '2020-11-09 11:31:25'),
(134, 5, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass) возраст MIX, друзей MIX', 1, 'temnik@mail.ru', '5.00', '1', '5.00', 'balance', '0', 0, 1, 'Login2:Pass2', '', '2020-11-09 11:31:39', '2020-11-09 11:31:37', '2020-11-09 11:31:39'),
(135, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', '0', 0, 1, 'Login6:Pass6', '', '2020-11-09 11:32:08', '2020-11-09 11:32:07', '2020-11-09 11:32:08'),
(136, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', '0', 0, 1, 'Login7:Pass7', '', '2020-11-09 11:32:21', '2020-11-09 11:32:20', '2020-11-09 11:32:21'),
(137, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара стало ограничено или товар закончился в момент покупки.', 0, 1, '', '', '2020-11-09 11:35:17', '2020-11-09 11:35:16', '2020-11-09 11:35:17'),
(138, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', 'www', 0, 1, 'Login8:Pass8', '', '2020-11-09 11:35:29', '2020-11-09 11:35:28', '2020-11-09 11:35:29'),
(139, 6, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass:Token) возраст MIX, пол Смешан, друзей 200+', 1, 'temnik@mail.ru', '33.50', '1', '33.50', 'balance', '', 0, 1, 'Login6:Pass6', '', '2020-11-09 11:36:00', '2020-11-09 11:35:59', '2020-11-09 11:36:00'),
(140, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', NULL, 0, 1, 'Login3:Pass3', '', '2020-11-09 11:36:45', '2020-11-09 11:36:23', '2020-11-09 11:36:45'),
(141, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', NULL, 0, 1, 'Login6:Pass6', '', '2020-11-09 12:13:16', '2020-11-09 11:38:35', '2020-11-09 12:13:16'),
(142, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', '', 0, 1, 'Login7:Pass7', '', '2020-11-09 12:13:50', '2020-11-09 12:13:50', '2020-11-09 12:13:50'),
(143, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'product_buy_denied_quantity', 0, 1, '', '', '2020-11-09 12:15:59', '2020-11-09 12:15:58', '2020-11-09 12:15:59'),
(144, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара стало ограничено или товар закончился в момент покупки.', 0, 1, '', '', '2020-11-09 12:16:36', '2020-11-09 12:16:35', '2020-11-09 12:16:36'),
(145, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара стало ограничено или товар закончился в момент покупки.', 0, 1, '', '', '2020-11-09 12:24:57', '2020-11-09 12:24:56', '2020-11-09 12:24:57'),
(146, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара стало ограничено или товар закончился в момент покупки. Напишите в тех-поддержку для решения проблемы. ', 0, 1, '', '', '2020-11-09 13:51:43', '2020-11-09 13:51:34', '2020-11-09 13:51:43'),
(147, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара стало ограничено или товар закончился в момент покупки. Напишите в тех-поддержку для решения проблемы. ', 0, 1, '', '', '2020-11-09 13:54:09', '2020-11-09 13:54:08', '2020-11-09 13:54:09'),
(150, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '1', '111.00', 'balance', 'Количество товара стало ограничено или товар закончился в момент покупки. Напишите в тех-поддержку для решения проблемы. ', 0, 1, '', '', '2020-11-09 13:55:10', '2020-11-09 13:55:00', '2020-11-09 13:55:10'),
(151, 7, 'Text eteette', 1, 'temnik@mail.ru', '111.00', '0', '0.00', 'balance', 'Количество товара ограничено или товар закончился.', 0, 1, '', '', '2020-11-09 13:56:09', '2020-11-09 13:56:07', '2020-11-09 13:56:09'),
(153, 5, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass) возраст MIX, друзей MIX', 1, 'temnik@mail.ru', '5.00', '12', '60.00', 'balance', 'Количество товара ограничено или товар закончился.', 0, 1, '', '', '2020-11-09 13:56:36', '2020-11-09 13:56:29', '2020-11-09 13:56:36'),
(154, 5, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass) возраст MIX, друзей MIX', 1, 'temnik@mail.ru', '5.00', '13', '65.00', 'balance', 'Количество товара ограничено или товар закончился.', 0, 1, '', '', '2020-11-09 13:57:06', '2020-11-09 13:57:04', '2020-11-09 13:57:06'),
(155, 5, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass) возраст MIX, друзей MIX', 1, 'temnik@mail.ru', '5.00', '1', '5.00', 'balance', '', 0, 1, 'Login3:Pass3', '', '2020-11-09 14:12:04', '2020-11-09 14:12:03', '2020-11-09 14:12:04'),
(156, 6, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass:Token) возраст MIX, пол Смешан, друзей 200+', 1, 'temnik@mail.ru', '33.50', '1', '33.50', 'balance', '', 0, 1, 'Login7:Pass7', '', '2020-11-09 14:13:03', '2020-11-09 14:13:02', '2020-11-09 14:13:03'),
(157, 6, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass:Token) возраст MIX, пол Смешан, друзей 200+', 1, 'temnik@mail.ru', '33.50', '1', '33.50', 'balance', '', 0, 1, 'Login8:Pass8', '', '2020-11-09 14:13:28', '2020-11-09 14:13:26', '2020-11-09 14:13:28'),
(158, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '2', '39.04', 'balance', '', 0, 1, 'Login8:Pass8\r\nLogin2:Pass2', '', '2020-11-09 14:13:58', '2020-11-09 14:13:55', '2020-11-09 14:13:58'),
(159, 4, 'VK (РФ - 100%, в логине ПОЧТА, актив 100%) ОТ 50 друзей +18 лет', 1, 'temnik@mail.ru', '19.52', '1', '19.52', 'balance', '', 0, 1, 'Login3:Pass3\r', NULL, '2020-11-10 18:48:49', '2020-08-08 18:48:59', '2020-08-08 18:48:59'),
(162, 6, 'VK - РФ+СНГ, АКТИВ, (Login/Phon:Pass:Token) возраст MIX, пол Смешан, друзей 200+', 1, 'temnik@mail.ru', '33.50', '1', '33.50', 'balance', '', 0, 1, 'Login2:Pass2\r', NULL, '2020-11-18 05:45:35', '2020-11-18 05:45:33', '2020-11-18 05:45:35');

-- --------------------------------------------------------

--
-- Структура таблицы `users`
--

CREATE TABLE `users` (
  `id` int(10) UNSIGNED NOT NULL,
  `name` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `email` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `email_verified_at` timestamp NULL DEFAULT NULL,
  `password` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL,
  `group` varchar(255) COLLATE utf8mb4_unicode_ci NOT NULL DEFAULT 'user',
  `balance` decimal(10,2) DEFAULT '0.00',
  `favorites` text COLLATE utf8mb4_unicode_ci,
  `last_login` timestamp NULL DEFAULT NULL,
  `last_payment` timestamp NULL DEFAULT NULL,
  `last_purchase` timestamp NULL DEFAULT NULL,
  `telegram` varchar(255) COLLATE utf8mb4_unicode_ci DEFAULT '',
  `remember_token` varchar(100) COLLATE utf8mb4_unicode_ci DEFAULT NULL,
  `created_at` timestamp NULL DEFAULT NULL,
  `updated_at` timestamp NULL DEFAULT NULL
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4 COLLATE=utf8mb4_unicode_ci;

--
-- Дамп данных таблицы `users`
--

INSERT INTO `users` (`id`, `name`, `email`, `email_verified_at`, `password`, `group`, `balance`, `favorites`, `last_login`, `last_payment`, `last_purchase`, `telegram`, `remember_token`, `created_at`, `updated_at`) VALUES
(1, 'Главный администратор', 'manager@akk-seller.online', NULL, '$2y$10$kubKOi3oZKWuUXND9nBx6exnN36uDc9oBhp.FreA7CqbBUnt4b5a.', 'admin', '684.94', '22,5', '2020-11-18 05:43:56', NULL, NULL, '+100000000', 'z2tNNJuVdIruM0qs3XaneRzBkxBVbK9y9mw42YvbEaJgPjups4gA07DxR9XN', '2020-11-04 09:50:45', '2020-11-18 05:45:35'),
(2, 'Технический аккаунт elite-designs', 'elitedesignsru@gmail.com', NULL, '$2y$10$enxYfOKU4UuFmL3PXjV0yOO/T5cjAUcrZVasIe0s9bwVO2zmeACdy', 'admin', '882.88', '', '2020-11-11 17:32:59', NULL, NULL, '@EliteDesignsRu', NULL, '2020-11-05 10:26:41', '2020-11-11 17:43:57'),
(3, 'Tester1', 'tester1@mail.ru', NULL, '$2y$10$6FVtZTLBH9dLc7xp8dzMz..kUVqu1iKY3Y9HqaAxjHX9lRs.m2GYG', 'user', '0.00', '', NULL, NULL, NULL, '123456', NULL, '2020-11-05 11:01:01', '2020-11-05 11:05:32'),
(4, 'Tester2', 'tester2@tester.ru', NULL, '$2y$10$1Udkv31.iSvckvVUjjY3wOkConIXcHAIakNxDWjFSYC3K0l5evKqC', 'user', NULL, '', NULL, NULL, NULL, '111111111111', NULL, '2020-11-07 21:15:36', '2020-11-07 21:22:39'),
(5, 'Tester3', 'tester3@mail.ru', NULL, '$2y$10$yaLT9WIVNLjtcUGc2lW9v.pbX.BSDz4RhjlFhxPCfJWqOEaeucu6e', 'user', '0.00', ',4,6', '2020-11-09 08:53:51', NULL, NULL, '123456123456', NULL, '2020-11-09 08:55:03', '2020-11-09 09:20:27'),
(6, 'Rom', 'flex.flex.18@gmail.com', NULL, '$2y$10$/p/6AXnPD2RLPr4UyPDn9OiKUAyC4YrPrYkDfF2lLqPbBjGgaLIGi', 'user', '0.00', NULL, '2020-11-11 16:18:53', NULL, NULL, '@1232131', 'wmclcQ2L561CYWWx03uAqFN4WezYScdvP8aWYaxzidUf9hS99GMM12HaXAu9', '2020-11-11 15:53:01', '2020-11-11 16:18:53'),
(7, 'asdsad', 'flex.flex.12@gmail.com', NULL, '$2y$10$ADM/dVSLrTu9pB.rFoEOp.iy5Nw8FkB5S17XYCVLskp6GUgVnDp2a', 'user', '0.00', NULL, NULL, NULL, NULL, 'sadsdas', NULL, '2020-11-11 16:22:44', '2020-11-11 16:22:44');

