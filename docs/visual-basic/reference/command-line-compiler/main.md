---
title: "/main | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/main (opción del compilador) [Visual Basic]"
  - "main (opción del compilador) [Visual Basic]"
  - "-main (opción del compilador) [Visual Basic]"
ms.assetid: 83fc339d-6652-415d-b205-b5133319b5b0
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# /main
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica la clase o el módulo que contiene el procedimiento `Sub Main`.  
  
## Sintaxis  
  
```  
/main:location  
```  
  
## Argumentos  
 `location`  
 Obligatorio.  Una especificación completa a la clase o módulo que contiene el procedimiento `Sub Main` que se va a llamar cuando el sistema se inicia.  Puede estar en el formulario **\/main:module** o **\/main:namespace.module**.  
  
## Comentarios  
 Use esta opción al crear un archivo ejecutable o un programa ejecutable de Windows.  Si se omite la opción **\/main**, el compilador busca un procedimiento `Sub Main` compartido válido en todas las clases y módulos públicos.  
  
 Vea [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md) para consultar una descripción de las distintas formas que puede tener el procedimiento `Main`.  
  
 Cuando `location` es una clase que hereda de <xref:System.Windows.Forms.Form>, el compilador proporciona un procedimiento `Main` predeterminado que inicia la aplicación si la clase no tiene ningún procedimiento `Main`.  Esto le permite compilar código en la línea de comandos que se creó en el entorno de desarrollo.  
  
 [!code-vb[VbVbalrCompiler#16](../../../visual-basic/reference/command-line-compiler/codesnippet/visualbasic/main_1.vb)]  
  
### Para establecer \/main en el entorno integrado de desarrollo \(IDE\) de Visual Studio  
  
1.  Tenga seleccionado un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  
  
     Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la ficha **Aplicación**.  
  
3.  Asegúrese de que no se active la casilla **Habilitar marco de trabajo de la aplicación**.  
  
4.  Modifique el valor en el cuadro **Objeto inicial**.  
  
## Ejemplo  
 El código siguiente compila `T2.vb` y `T3.vb`, y especifica que el procedimiento `Sub Main` se encontrará en la clase `Test2`.  
  
```  
vbc t2.vb t3.vb /main:Test2  
```  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\/target](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/es-es/9d030b60-e148-4366-a462-69532f02294c)   
 [Procedimiento Main en Visual Basic](../../../visual-basic/programming-guide/program-structure/main-procedure.md)