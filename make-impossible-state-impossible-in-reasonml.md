# Summary
https://gist.github.com/busypeoples/ab2f993843f23614232a1f8500a4b542

- What we have noticed in the initial iteration is that we need an inclusive-or meaning something can be A or B but can also be A and B. With our previous approach we were not able to model this properly.
- You might have noticed that we're always dealing with the same situation here. We can have A or B, but also A and B. So we can abstract this situation by defining a these type.
```reasonml
type these 'a 'b =
  | This 'a
  | That 'b
  | These 'a 'b;
```