# ilyae.github.io
<!DOCTYPE html>
<html>
<head>
    <title>Мой сайт</title>
</head>
<body>
    import http from 'k6/http';

export default function () {
  const res = http.get('https://student.github.io/techcampus-qa/');
}
</body>
</html>
