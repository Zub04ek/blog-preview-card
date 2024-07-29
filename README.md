# Frontend Mentor - Blog preview card solution

![Design preview for the Blog preview card coding challenge](./preview.jpg)

This is a solution to the [Blog preview card challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/blog-preview-card-ckPaj01IcS).

## Links

- Live Site URL: [https://zub04ek.github.io/blog-preview-card/](https://zub04ek.github.io/blog-preview-card/)
- Frontend Mentor - [@Zub04ek](https://www.frontendmentor.io/profile/Zub04ek)

## Built with

- Semantic HTML5 markup
- CSS custom properties
- Flexbox
- CSS Clamp
- Mobile-first workflow

## What I learned

One of the tasks of this challenge was to find a way to reduce the font size for smaller screens without using media queries. It was a revelation for me to find out about **CSS function clamp()** that can linearly scale text between a set of minimum and maximum sizes as the viewport’s width increases. Here’s how it works. It takes three values: 

```
clamp(minimum, preferred, maximum);
```
where:
- minimum value — equal to minimum font size
- maximum value — equal to maximum font size
- preferred value — determines how typography scales and will depend on the viewport size

Pixel values for min and max are not accessible so I converted the px values to rem values by dividing the px values by 16 (the default browser font size). Calculating the correct preferred value can be tricky, so I used some tools to generate it (links are below).

According to Figma's designs, we had 2 basic screen widths: 375px for mobile and 1440px for desktop. For example, the paragraph with the date has a font size of 12px for mobile and 14px for desktop. After converting to rem and calculating, here's how it looks in my project:

```css
.date {
  font-size: clamp(0.75rem, 0.7058rem + 0.188vw, 0.875rem);
}
```

You can find more explanations in the useful resources below.

## Useful resources

All these resources helped me to understand the CSS clamp() function:

- [Linearly Scale font-size with CSS clamp() Based on the Viewport](https://css-tricks.com/linearly-scale-font-size-with-css-clamp-based-on-the-viewport/#for-those-who-dont-mind-that-edge-case) - This is a great article, with lots of examples and graphs + a small tool to generate the right arguments for the clamp function;
- [Modern Fluid Typography Using CSS Clamp](https://www.smashingmagazine.com/2022/01/modern-fluid-typography-css-clamp/) - Another useful article with examples and formulas. I'd recommend it to anyone still learning this concept;
- [min(), max(), and clamp() CSS Functions](https://ishadeed.com/article/css-min-max-clamp/) - This article explains not only the clamp() function, but also the min() and max() functions, and shows how to use them not only for typography, but also for widths or padding;
- [CSS min(), max(), and clamp()](https://web.dev/articles/min-max-clamp);
- [Min-Max-Value Interpolation](https://min-max-calculator.9elements.com/) - the handy online tool with an attractive appearance;

## Acknowledgments

While reviewing my previous challenge, I received a useful tip from [@TheBeyonder616](https://www.frontendmentor.io/profile/TheBeyonder616) about using the CSS clamp function to make the layout more responsive. This was new to me and I decided to use it for this assignment as well, especially for the font sizes and width of the card.
