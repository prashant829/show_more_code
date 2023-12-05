# show_more_code
Show More Button code in jquery for bigger paragraph
<---- html ---->

body.page

  main.page__main
  
    article.art
      h1.art__title Something Awesome
      p#artDesc.art__desc Lorem ipsum dolor sit amet consectetur adipisicing elit. Fugiat dolores odit eum ex quos, repellat incidunt praesentium earum minus. Vero debitis quas dicta laborum, tenetur quia temporibus autem fuga voluptatibus.
      
      button(onclick = "toggleText(this)").art__btn.primary-btn Read less

<---- css ---->
@import "https://unpkg.com/open-props"

button
  
  // typography
  font: inherit

.page
  
  // color
  color: var(--gray-9)
  background:
    color: var(--gray-0)
  
  // grid
  display: grid
  grid:
    template:
      areas: "main"
    
  // size
  min:
    height: 100vh
      
  // typography
  font:
    family: var(--font-sans)
  
  &__main
    
    // grid
    grid:
      area: main
    
.art
  
  // size
  padding: var(--size-6) var(--size-3)
  
  &__title
    
    // size
    margin:
      bottom: var(--size-4)
    
    // typography
    font:
      weight: var(--font-weight-6)
      size: var(--font-size-fluid-2)
      
  &__desc
    
    // typography
    line:
      height: var(--font-lineheight-2)
      
  &__btn
    
    // position
    margin:
      top: var(--size-4)
      
.primary-btn
  
  // color
  color: var(--gray-0)
  background: 
    color: var(--gray-9)
    
  // size
  border: 0
  padding: var(--size-3)
  
  // state
  cursor: pointer
  
  &:hover
  
    // color
    background:
      color: var(--gray-7)

<---- js ---->
const artDesc = document.getElementById("artDesc");
const copiedTxt = artDesc.textContent;

function toggleText(btn) {
  if (artDesc.textContent.length > 50) {
    artDesc.textContent = `${artDesc.textContent.slice(0, 47)}...`;
    btn.textContent = "Read more";
  } else {
    artDesc.textContent = copiedTxt;
    btn.textContent = "Read less";
  }

  return artDesc.textContent;
}


