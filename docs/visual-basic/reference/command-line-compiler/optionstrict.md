---
title: "/optionstrict | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/optionstrict"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/optionstrict (opción del compilador) [Visual Basic]"
  - "optionstrict (opción del compilador) [Visual Basic]"
  - "-optionstrict (opción del compilador) [Visual Basic]"
ms.assetid: c7b10086-0fa4-49db-b3c8-4ae0db5957da
caps.latest.revision: 17
caps.handback.revision: 17
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /optionstrict
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Fuerza una semántica de tipos estricta que limita las conversiones implícitas.  
  
## Sintaxis  
  
```  
/optionstrict[+ | -]  
/optionstrict[:custom]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Opcional.  La opción `/optionstrict+` restringe la conversión de tipos implícita.  El valor predeterminado de esta opción es `/optionstrict-`.  La opción `/optionstrict+` es igual que `/optionstrict`.  Puede utilizar ambas en semántica de tipos permisiva.  
  
 `custom`  
 Obligatorio.  Genera una advertencia cuando no se respeta la semántica de lenguaje estricta.  
  
## Comentarios  
 Cuando la opción `/optionstrict+` está habilitada, sólo se puede realizar implícitamente las conversiones de ampliación de tipos.  Las conversiones de restricción de tipos, como la asignación de un objeto de tipo `Decimal` a un objeto de tipo Integer, se notificarán como errores.  
  
 Para generar las advertencias en las conversiones de restricción de tipos implícitas, utilice `/optionstrict:custom`.  Utilice `/nowarn:numberlist` para omitir advertencias determinadas y `/warnaserror:numberlist` para tratar determinadas advertencias como errores.  
  
### Para establecer \/optionstrict en el entorno de desarrollo integrado de Visual Studio  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**. Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Compilar**.  
  
3.  Modifique el valor en el cuadro **Option Strict**.  
  
### Para establecer \/optionstrict mediante programación  
  
-   Vea [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## Ejemplo  
 La siguiente línea compila `Test.vb` y utiliza semántica estricta de tipos.  
  
```  
vbc /optionstrict+ test.vb  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/optioncompare](../../../visual-basic/reference/command-line-compiler/optioncompare.md)   
 [\/optionexplicit](../../../visual-basic/reference/command-line-compiler/optionexplicit.md)   
 [\/optioninfer](../../../visual-basic/reference/command-line-compiler/optioninfer.md)   
 [\/nowarn](../../../visual-basic/reference/command-line-compiler/nowarn.md)   
 [\/warnaserror](../../../visual-basic/reference/command-line-compiler/warnaserror.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Option Strict \(Instrucción\)](../../../visual-basic/language-reference/statements/option-strict-statement.md)   
 [Valores predeterminados de Visual Basic, Proyectos, Opciones \(Cuadro de diálogo\)](/visual-studio/ide/reference/visual-basic-defaults-projects-options-dialog-box)