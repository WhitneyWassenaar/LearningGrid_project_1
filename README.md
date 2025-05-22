# LearningGrid_project_1
The assignment I practiced is <A href="https://github.com/hogeschoolnovi/frontend-css-grid">frontend-css-grid</a> made by <a href="https://github.com/novaeeken">novaeeken</a> from Novi Hogeschool.
<br>The finished project should look like this
![image](https://github.com/user-attachments/assets/46d37ec0-34a8-49e6-ae87-ff390eff6858)


## Thursday | 22-5-2025 | 11:27
With this project I started with the mobile version first. Because this is the workflow I currently know for responsive webdesign. Grid is totally new to me so I had to focus very well because I was used to using flexbox.<br>
A challenge for me was to create the empty space between the grid items E and F. Every grid item is 50px high except grid-item B, this item had to be dynamic so I set the height to <code>auto</code>. <br>The empty space had to be 50px high as well.
<br>It took me a while to understand how to use: <code>grid-template-columns</code> & <code>grid-template-rows</code>.

<hr>

<bold>Problems</bold>
1. The grid disappears.
2. No matter what I did I could not create the empty space with a height of 50%

### Mobile version grid with mistakes
![image](https://github.com/user-attachments/assets/2ac398c2-c7f5-48b3-aba0-1ddd4a4e49e6)

<bold>HTML</bold>
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <div class="container">
        <div class="itemA">A</div>
        <div class="itemB">B: Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa cum dolore perferendis molestias minus iusto maiores. Nulla rem cum quam eaque animi nihil unde esse, maxime quos sint ea omnis, corrupti iure aliquam fuga ipsum modi? Impedit omnis quibusdam rem aperiam corrupti dolores animi ratione inventore. Dignissimos ea quas voluptatibus molestias reprehenderit alias unde harum totam perspiciatis minima nulla quod, sit sed aperiam temporibus perferendis repellendus illum nesciunt necessitatibus quisquam quaerat tenetur ratione. Reprehenderit, totam asperiores? Nostrum magni iure sint at voluptas culpa, soluta distinctio impedit blanditiis esse! Aliquam nostrum maxime laudantium eaque repellat, tenetur asperiores quaerat consequatur ut labore rem mollitia? Placeat aperiam quae error veniam cupiditate consequuntur numquam incidunt, maiores enim aspernatur sequi a voluptatum sunt corrupti, ratione facilis obcaecati quidem illo! Ea mollitia voluptatibus, ratione maiores repellat aperiam! Enim nostrum ullam delectus unde sit! Beatae sapiente ut non hic natus quasi. Atque maiores molestias fuga quo dolor!</div>
        <div class="itemC">C</div>
        <div class="itemD">D</div>
        <div class="itemE">E</div>
        <div class="itemF">F</div>
    </div>
    
</body>
</html>
```
<bold>CSS</bold>
```

.container {
    display: grid;
    grid-template-columns: auto;
    grid-template-rows: 50px auto 50px 50px 50px 50px;
    row-gap: 16px;
    column-gap:16px;
    padding: 16px;
    background-color: rgb(240, 234, 231);
    grid-template-areas: 
    'h'
    'm'
    'h'
    'h'
    'h'
    '.'
    'h';
}

.container  div {
    background-color: rgb(217, 81, 81);
    color:white;
    display: flex;
    justify-content: center;
    padding: 10px;
}

/*
.itemA {
    grid-area: h;
}

.itemB {
    grid-area: m;
}

.itemC {
    grid-area: h;
}

.itemD {
    grid-area:h;
}

.itemE {
    grid-area: h;
}

.itemF {
    grid-area: h;
}

*/

```

<hr>

### Mobile version final result
<bold>Solution</bold>
>When creating a grid. I found out that every item must have their own grid area name assigned or else the grid doesn’t work. If I wanted to add empty space that space must also be declared in grid-template-rows because according to the exercise there is a fixed height of 50px.
To add the empty space I should have written ' . ' between the items I want to have empty space.

![image](https://github.com/user-attachments/assets/7e46bd34-52ac-4c17-9ec2-766cd324df86)
<bold>HTML</bold>
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <div class="container">
        <div class="itemA">A</div>
        <div class="itemB">B: Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa cum dolore perferendis molestias minus iusto maiores. Nulla rem cum quam eaque animi nihil unde esse, maxime quos sint ea omnis, corrupti iure aliquam fuga ipsum modi? Impedit omnis quibusdam rem aperiam corrupti dolores animi ratione inventore. Dignissimos ea quas voluptatibus molestias reprehenderit alias unde harum totam perspiciatis minima nulla quod, sit sed aperiam temporibus perferendis repellendus illum nesciunt necessitatibus quisquam quaerat tenetur ratione. Reprehenderit, totam asperiores? Nostrum magni iure sint at voluptas culpa, soluta distinctio impedit blanditiis esse! Aliquam nostrum maxime laudantium eaque repellat, tenetur asperiores quaerat consequatur ut labore rem mollitia? Placeat aperiam quae error veniam cupiditate consequuntur numquam incidunt, maiores enim aspernatur sequi a voluptatum sunt corrupti, ratione facilis obcaecati quidem illo! Ea mollitia voluptatibus, ratione maiores repellat aperiam! Enim nostrum ullam delectus unde sit! Beatae sapiente ut non hic natus quasi. Atque maiores molestias fuga quo dolor!</div>
        <div class="itemC">C</div>
        <div class="itemD">D</div>
        <div class="itemE">E</div>
        <div class="itemF">F</div>
    </div>
    
</body>
</html>
```

<bold>CSS</bold>
```
.container {
    display: grid;
    grid-template-columns: auto;
    grid-template-rows: 50px auto 50px 50px 50px 50px 50px;
    row-gap: 16px;
    column-gap:16px;
    padding: 16px;
    background-color: rgb(240, 234, 231);
    grid-template-areas: 
    'A'
    'B'
    'C'
    'D'
    'E'
    '.'
    'F'
    ;
}

.container  div {
    background-color: rgb(217, 81, 81);
    color:white;
    display: flex;
    justify-content: center;
   align-items:center;

    padding: 10px;
}


.itemA {
    grid-area: A;
}

.itemB {
    grid-area: B;
}

.itemC {
    grid-area: C;
}

.itemD {
    grid-area:D;
}

.itemE {
    grid-area: E;
}

.itemF {
    grid-area: F;
}
```

<hr>

### Building the desktop version
After reading and watching a bunch of tutorials I still didn't understand the way grid works, especially when building dynamic layouts. I was so confused by writing down the grid-template-areas that I almost gave up. Then I just looked at my code and started talking to myself out loud what I wanted to do .<br>
1. First I started drawing the gridlines on the example.
 ![image](https://github.com/user-attachments/assets/72be0b42-4d45-4efc-b093-1aad3689565a)

3. Then I counted the amount of columns and rows I saw in my sketch.
   ![image](https://github.com/user-attachments/assets/76ceac97-28f8-4ab0-8233-ff3a5d11a0d4)
   
4. Now I have all the information needed to fill in the properties
If you look at the columns, you can see that they are divided in 3 even parts. I use <code>fr</code> to declare those parts in <code>grid-template-columns</code> with <code>1fr 1fr 1fr</code>.

5. Now we look at the rows, they have different heights and should be declared in <code>grid-template-rows</code>. You can see that the first row is 50px in height because it is parallel to item A. <br>For the second row you have to use your math skills.<br> Item C is 240px high but is already cut of by the first row, which is 50px high. The only thing you need to do is 240px - 50px = 190px. <br>The height of the second row is 190px.
6. The thirth row is 100px high, you can see it from item D.
7. The fourth row is a dynamic one. You should set it to <code>auto</code>
8. The last row is 50px.
9 To know how to declare the grid items into the grid-template-areas, you can  make a reference by indicating the names in every box. Now we can declare the grid-area names of the items into the <code>grid-template-areas</code>
 ![image](https://github.com/user-attachments/assets/12ee393a-ff9d-42da-a51c-b6fd96685d0e)
    ![image](https://github.com/user-attachments/assets/ff834558-725e-405e-b93d-f6d1701d6dda)

<hr>

### Desktop version final result

![image](https://github.com/user-attachments/assets/d2f008a1-5842-4ee7-812b-249e8aaa5f35)

<bold>HTML</bold>
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>

    <div class="container">
        <div class="itemA">A</div>
        <div class="itemB">B: Lorem ipsum dolor sit amet consectetur adipisicing elit. Ipsa cum dolore perferendis molestias minus iusto maiores. Nulla rem cum quam eaque animi nihil unde esse, maxime quos sint ea omnis, corrupti iure aliquam fuga ipsum modi? Impedit omnis quibusdam rem aperiam corrupti dolores animi ratione inventore. Dignissimos ea quas voluptatibus molestias reprehenderit alias unde harum totam perspiciatis minima nulla quod, sit sed aperiam temporibus perferendis repellendus illum nesciunt necessitatibus quisquam quaerat tenetur ratione. Reprehenderit, totam asperiores? Nostrum magni iure sint at voluptas culpa, soluta distinctio impedit blanditiis esse! Aliquam nostrum maxime laudantium eaque repellat, tenetur asperiores quaerat consequatur ut labore rem mollitia? Placeat aperiam quae error veniam cupiditate consequuntur numquam incidunt, maiores enim aspernatur sequi a voluptatum sunt corrupti, ratione facilis obcaecati quidem illo! Ea mollitia voluptatibus, ratione maiores repellat aperiam! Enim nostrum ullam delectus unde sit! Beatae sapiente ut non hic natus quasi. Atque maiores molestias fuga quo dolor!</div>
        <div class="itemC">C</div>
        <div class="itemD">D</div>
        <div class="itemE">E</div>
        <div class="itemF">F</div>
    </div>
    
</body>
</html>
```

<bold>CSS</bold>
```
/*Mobile*/
.container {
    display: grid;
    grid-template-columns: auto;
    grid-template-rows: 50px auto 50px 50px 50px 50px 50px;
    row-gap: 16px;
    column-gap:16px;
    padding: 16px;
    background-color: rgb(240, 234, 231);
    grid-template-areas: 
    'A'
    'B'
    'C'
    'D'
    'E'
    '.'
    'F'
    ;
}

.container  div {
    background-color: rgb(217, 81, 81);
    color:white;
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 10px;
}

.itemA {
    grid-area: A;
}

.itemB {
    grid-area: B;
}

.itemC {
    grid-area: C;
}

.itemD {
    grid-area:D;
}

.itemE {
    grid-area: E;
}

.itemF {
    grid-area: F;
}
/*Desktop*/
@media (min-width:1000px){

    .container {
        grid-template-columns: 1fr 1fr 1fr;
        grid-template-rows: 50px 190px 100px auto 50px;
        grid-template-areas: 
        'A C C'
        'B C C'
        'B E D'
        'B E .'
        'F F F';
}
 }
```
