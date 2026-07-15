# Doctor GPS Admin

Отдельная админ-панель для пользователей, тарифов, подписок, платежей и отчётов Doctor GPS.

## Установка

1. Выполнить `supabase/doctor-gps-payments.sql` в SQL Editor проекта Supabase.
2. Добавить первого администратора:
   `insert into public.doctor_gps_admins(user_id) values ('UUID_ПОЛЬЗОВАТЕЛЯ');`
3. Скопировать URL проекта и publishable key в `config.js`.
4. Развернуть Edge Functions `doctor-gps-create-payment` и `doctor-gps-payment-webhook`.
5. Секреты задавать только через `supabase secrets set`, никогда не помещать их в `config.js`.

Необходимые секреты: `YOOKASSA_SHOP_ID`, `YOOKASSA_SECRET_KEY`, `ROBOKASSA_MERCHANT_LOGIN`, `ROBOKASSA_PASSWORD1`, `ROBOKASSA_PASSWORD2`, `PAYMENT_RETURN_URL`.

Цена и активный провайдер управляются из админки. Секреты провайдеров в браузер не передаются.
