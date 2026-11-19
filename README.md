# ilyae.github.io
import http from 'k6/http';

export default function () {
  const res = http.get('https://student.github.io/techcampus-qa/');
}
