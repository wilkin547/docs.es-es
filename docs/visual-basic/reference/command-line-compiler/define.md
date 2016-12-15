---
title: "/define (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "/d (opción del compilador) [Visual Basic]"
  - "/define (opción del compilador) [Visual Basic]"
  - "d (opción del compilador) [Visual Basic]"
  - "-d (opción del compilador) [Visual Basic]"
  - "define (opción del compilador) [Visual Basic]"
  - "-define (opción del compilador) [Visual Basic]"
ms.assetid: f735c57d-1cf9-4f2f-a26f-0de630fd4077
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# /define (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Permite definir constantes condicionales para el compilador.  
  
## Sintaxis  
  
```  
/define:["]symbol[=value][,symbol[=value]]["] ' -or- /d:["]symbol[=value][,symbol[=value]]["]  
```  
  
## Argumentos  
  
|||  
|-|-|  
|Término|Definición|  
|`symbol`|Requerido.  Símbolo que se va a definir.|  
|`value`|Opcional.  Valor que se va a asignar a `symbol`.  Si `value` es una cadena, puede insertarse en secuencias de barra diagonal inversa\/comillas \(\\"\) en lugar de entre comillas.  Si no se especifica ningún valor, se considera como verdadero.|  
  
## Comentarios  
 La opción `/define` tiene un efecto similar a usar una directiva de preprocesador `#Const` en el archivo de origen, salvo por el hecho de que las constantes con `/define` son públicas y se aplican a todos los archivos del proyecto.  
  
 Los símbolos creados por esta opción se pueden usar con la directiva `#If`...`Then`...`#Else` para compilar archivos de origen condicionalmente.  
  
 `/d` es la forma abreviada de `/define`.  
  
 Se pueden definir varios símbolos con `/define`; use una coma para separar las definiciones de símbolos.  
  
||  
|-|  
|Para definir\/establecer en el entorno de desarrollo integrado de Visual Studio|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**.  En el menú **Proyecto**, haga clic en **Propiedades**.  Para obtener más información, vea [Introduction to the Project Designer](http://msdn.microsoft.com/es-es/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Haga clic en **Avanzado**.<br />4.  Cambie el valor del cuadro **Constantes personalizadas**.|  
  
## Ejemplo  
 En el siguiente código se definen y usan dos constantes de compilador condicionales.  
  
 [!code-vb[VbVbalrCompiler#45](../../../visual-basic/reference/command-line-compiler/codesnippet/VisualBasic/define_1.vb)]  
  
## Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [\#If...Then...\#Else \(Directivas\)](../../../visual-basic/language-reference/directives/if-then-else-directives.md)   
 [\#Const \(Directiva\)](../../../visual-basic/language-reference/directives/const-directive.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)