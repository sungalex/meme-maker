# MEME Maker

Meme Maker with canvas API (Vanilla Javascript)

- [Nomadcorders: 바닐라 JS로 그림 앱 만들기](https://nomadcoders.co/javascript-for-beginners-2/)

- [canvas API](https://developer.mozilla.org/ko/docs/Web/API/Canvas_API)

- [HomePage : https://sungalex.github.io/meme-maker/](https://sungalex.github.io/meme-maker/)

## Painting Board

- Mouse Painting

- Line Width

- Paint Color

- Filling Mode

- Eraser

## Adding Image, Adding Text, Saveing Image

- Adding Image

  ```js
  function onFileChange(event) {
    const file = event.target.files[0];
    const url = URL.createObjectURL(file);
    const image = new Image();
    image.src = url;
    image.onload = function () {
      ctx.drawImage(image, 0, 0, CANVAS_WIDTH, CANVAS_HEIGHT);
      fileInput.value = null;
    };
  }
  ```

- Adding Text : on Double Click Canvas

  ```js
  function onDoubleClick(event) {
    const text = textInput.value;
    if (text !== "") {
      ctx.save();
      ctx.lineWidth = 1;
      ctx.font = "68px sans-serif";
      ctx.fillText(text, event.offsetX, event.offsetY);
      ctx.restore();
    }
  }
  ```

- Saving Image

  ```js
  function onSaveClick() {
    const url = canvas.toDataURL();
    const a = document.createElement("a");
    a.href = url;
    a.download = "myMeme.png";
    a.click();
  }
  ```
