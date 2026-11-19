# ilyae.github.io
import http from 'k6/http';
import { parseHTML } from 'k6/html';
import { check, sleep } from 'k6';

export default function () {
  // 1. Отправляем GET-запрос к нашему HTML-приложению
  const res = http.get('https://github.com/ilyaeremkin9012005-ui/ilyae.github.io');

  // 2. Разбираем HTML-документ для поиска тегов
  const doc = parseHTML(res.body);

  // 3. Проверяем статус, заголовок ответа и тег h1
  check(res, {
    'статус ответа 200 OK': (r) => r.status === 200,
    'тип контента text/html': (r) =>
      r.headers['Content-Type'] && r.headers['Content-Type'].includes('text/html'),
    'заголовок h1 содержит TechCampus': () => doc.find('h1').text().includes('TechCampus'),
  });

  // 4. Пауза 1 секунда
  sleep(1);
}
