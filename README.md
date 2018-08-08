# Collage

Like Masonry, Collage creates a deterministic grid layout that can
absolutely position and virtualize images.

Extracted from gestalt and ported to TypeScript by Kronuz.

Usage here:
https://pinterest.github.io/gestalt/#/Collage


```jsx
import * from React from 'react';
import Collage from 'collage';

class Mask extends React.Component<{ width: number, height: number }> {
  render() {
    return <div />
  }
}

export const Example = () => (
  <Collage
    columns={3}
    height={300}
    width={300}
    renderImage={({ index, width, height }) => {
      const images = [
        {
          color: 'rgb(111, 91, 77)',
          naturalHeight: 751,
          naturalWidth: 564,
          src: '${stock1}',
        },
        {
          color: 'rgb(231, 186, 176)',
          naturalHeight: 200,
          naturalWidth: 98,
          src: '${stock2}',
        },
        {
          color: '#000',
          naturalHeight: 300,
          naturalWidth: 200,
          src: '${stock3}',
        },
        {
          color: '#000',
          naturalHeight: 517,
          naturalWidth: 564,
          src: '${stock4}',
        },
        {
          color: '#000',
          naturalHeight: 806,
          naturalWidth: 564,
          src: '${stock5}',
        },
        {
          color: '#000',
          naturalHeight: 200,
          naturalWidth: 200,
          src: '${stock6}',
        },
      ];
      const image = images[index];
      return (
        <Mask width={width} height={height}>
          <img
            alt="collage image"
            color={image.color}
            src={image.src}
          />
        </Mask>
      );
    }}
  />
);
```
