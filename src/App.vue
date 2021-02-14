<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <ListStories :listStories="listStories" />
  </div>
</template>

<script>
// import HelloWorld from '@/components/HelloWorld'
import ListStories from "@/components/ListStories";
export default {
  name: "App",
  data() {
    return {
      listStories: [
        {
          _id: "1",
          heading: "Hôm nay, Chủ nhật ngày 14/2/2021",
          content:
            "<p>Chắc hôm nay fb nhà nhà up ảnh valentine các kiểu. Còn mình hôm nay làm cái web đơn giản cũng gọi là kỉ niệm tròn 1 năm, kể từ ngày tỏ tình với crush :3. Cảm ơn c trong năm qua vẫn coi mình là bạn, vẫn chơi cùng mình, dù ko nhiều nhưng mình vẫn rất vui :3</p>",
          footer: "",
        },
        {
          _id: "2",
          heading: "",
          content:
            "<p>Dù gặp c khá nhiều nhưng ko hiểu sao mình vẫn cảm thấy hồi hộp và bối rối (chỉ giảm bớt chứ chưa bao h hết cảm giác đó), nói chuyện thì nhạt nhẽo, chính xác là chả biết bắt chuyện như nào, kể cả gặp mặt hay ib. Buồn lắm, ko biết bao giờ mới sửa được tật NHẠT đây?? :<</p>",
          footer: "",
        },
        {
          _id: "3",
          heading: "",
          content:
            "<p>Cũng không quên cảm ơn 2 người bạn của mình (xin phép ko nói tên :3), nếu ko có 2 bạn thì chắc có lẽ mình rủ mãi crush cũng chả chịu đi chơi cùng mình đâu (2 bạn chắc tự biết nên nếu có xem video này thì cũng đừng cmt gì lộ quá ko là toi mình đấy :3)</p>",
          footer: "",
        },
        {
          _id: "4",
          heading: "",
          content:
            "<p>Mình thì vẫn thích c nhiều lắm crush ơi, cho đến hiện tại thì ko ngày nào là c ko xuất hiện trong đầu mình cả :3 Mình không muốn chúng ta chỉ dừng lại ở bạn bè, hiện tại mình cần thời gian để phát triển bản thân và đợi thời điểm thích hợp sẽ tỏ tình version 2 với c (đấy là mình còn crush c và c vẫn chưa yêu ai nhé :3)</p>",
          footer: "",
        },
        {
          _id: "5",
          heading: "Valentine cũng như mồng 3 tết",
          content:
            "<p>Chắc cũng hết rồi nên cuối cùng, chúc cho tất cả nhưng ai xem đến cuối video có 1 năm sức khỏe dồi dào, hạnh phúc bên gia đình và gặp nhiều may mắn trong cuộc sống. </p><p>Chúc những ai ko có ngy và muốn có ngy thi sẽ sớm có ngy cho mình :3, những đôi yêu nhau sẽ mãi hạnh phúc bên người mình yêu, mọi giận hờn sẽ biến mất nhanh chóng!!</p>",
          footer: "Happy new year and valentine day!!!",
        },
      ],
    };
  },
  components: {
    // HelloWorld
    ListStories,
  },
};
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Cormorant+Upright:wght@300;400;500;600;700&family=Dancing+Script:wght@400;500;600;700&family=Pacifico&display=swap');

$colorWhite: #f1f1f1;
$colorBlack: #010101;
$colorPink: rgb(241, 28, 160);
$colorLightPurple: rgb(190, 162, 255);

html,
*,
*::after,
*::before {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html { 
  height: 100%;
}

body {
  font-family: Arial, Helvetica, sans-serif;
  color: $colorWhite;
  height: 100%;
  background-color: $colorLightPurple;
  #app {
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    background-image: url('./assets/images/i-love-you-valentine-s-day-background_23-2148393513.jpg');
    background-repeat: no-repeat;
    background-size: cover;
    background-attachment: fixed;
    background-position: center;
    #list-stories {
      position: relative;
      width: 60rem;
      height: 14rem;
      display: flex;
      justify-content: center;
      align-items: center;
      background-color: $colorPink;
      border-radius: 1.5rem;
      box-shadow: 1rem .5rem 3rem .75rem $colorWhite;
      .story-component {
        position: absolute;
        padding: 5rem 2rem;
      }
    }
  }
}

@media screen and (max-width: 1920px) and (min-width: 1633px){
  html {
    font-size: 24px;
  }
}
@media screen and (max-width: 1632px) and (min-width: 1441px){
  html {
    font-size: 20px;
  }
}
@media screen and (max-width: 1440px) and (min-width: 1281px){
  html {
    font-size: 18px;
  }
}
@media screen and (max-width: 1280px) and (min-width: 1025px){
  html {
    font-size: 14px;
  }
}
@media screen and (max-width: 1024px) and (min-width: 769px){
  html {
    font-size: 12px;
  }
}
</style>
