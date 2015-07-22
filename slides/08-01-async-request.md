#### Асинхронні операції

<small>Запит:</small>

POST /videos

```js
{
    "source": "https://aws.domain.com/home-video-ep-99.mp4",
    "codec": "FFmpeg",
    "type": "encode-video"
}
```

<small>Відповідь:</small>

Headers:

- Status: 202 Accepted

- Location: /queue/32233