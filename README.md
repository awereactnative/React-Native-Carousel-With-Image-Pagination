# React-Native-Carousel-With-Image-Pagination
# Introduction

In this, we will discuss how to integrate Carousel in a React Native application.
Carousels are widely used by many big websites, such as Amazon, Flipkart, etc. The same design element has been ported to mobile apps like Tinder, which uses swipe animation.

# Demo 
![Hero_Image_1](https://user-images.githubusercontent.com/86215353/181409395-946e2a4e-9711-4f02-80b3-b5c32933e155.gif)


# Installation
```
npm i react-native-snap-carousel
```

# Example
```js
import React, {useState, useRef} from 'react';
import {Text, View, Dimensions, Image} from 'react-native';
import Carousel, {Pagination} from 'react-native-snap-carousel';

export const SLIDER_WIDTH = Dimensions.get('window').width + 30;
export const ITEM_WIDTH = Math.round(SLIDER_WIDTH * 0.8);

const data = [
  {
    id: 1,
    name: 'React JS',
    url: 'https://icon-library.com/images/react-icon/react-icon-29.jpg',
  },
  {
    id: 2,
    name: 'JavaScript',
    url: 'https://upload.wikimedia.org/wikipedia/commons/3/3b/Javascript_Logo.png',
  },
  {
    id: 3,
    name: 'Node JS',
    url: 'https://upload.wikimedia.org/wikipedia/commons/6/67/NodeJS.png',
  },
];

const renderItem = ({item}) => {
  return (
    <View
      style={{
        borderWidth: 1,
        padding: 20,
        borderRadius: 20,
        alignItems: 'center',
        backgroundColor: 'lightgreen',
      }}>
      <Image source={{uri: item.url}} style={{width: 200, height: 200}} />
      <Text style={{marginVertical: 10, fontSize: 20, fontWeight: 'bold'}}>
        {item.name}
      </Text>
    </View>
  );
};

const App = () => {
  const [index, setIndex] = useState(0);
  const isCarousel = useRef(null);
  return (
    <View style={{paddingTop: 200,
      alignItems: 'center'}}>
      <Carousel
        ref={isCarousel}
        data={data}
        renderItem={renderItem}
        sliderWidth={SLIDER_WIDTH}
        itemWidth={ITEM_WIDTH}
        onSnapToItem={index => setIndex(index)}
      />
      <Pagination
        dotsLength={data.length}
        activeDotIndex={index}
        carouselRef={isCarousel}
        dotStyle={{
          width: 10,
          height: 10,
          borderRadius: 5,
          marginHorizontal: 8,
          backgroundColor: '#F4BB41',
        }}
        tappableDots={true}
        inactiveDotStyle={{
          backgroundColor: 'black',
          // Define styles for inactive dots here
        }}
        inactiveDotOpacity={0.4}
        inactiveDotScale={0.6}
      />
    </View>
  );
};

export default App;
```

# Tutorial

Coming Soon...
