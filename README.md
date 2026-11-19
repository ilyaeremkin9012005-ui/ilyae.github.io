# ilyae.github.io
<!DOCTYPE html>
<html>
<body>
    import http from 'k6/http';

export default function () {
  const res = http.get('https://ilyae.github.io/techcampus-qa/');
}
</body>
</html>
