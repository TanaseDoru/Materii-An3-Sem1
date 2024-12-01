```flex
%option noyywrap     -> pentru ca programul sa mearga
%{ -> programul efectiv
  

%}

  

%% -> Sectiunea de reguli

%%

  
  

int main() -> folosit pentru a lansa analizatorul lexical

{

  

}
```

flex *filename* -> compliare codul nostru va genera un program in c(ex lex.yy.c)
gcc *lex.yy.c* -o ex0 

```c
printf("Text: %s", yytext);
//sau
printf("Number: %d", atoi(yytext));
```

>[!IMPORTANT]
>Pentru a iesi dintr-un program lex se foloseste combinatia de taste **CTRL + D**

