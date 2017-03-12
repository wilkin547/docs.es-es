---
title: "/codepage (C# Compiler Options) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
f1_keywords: 
  - "/codepage"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "/codepage compiler option [C#]"
  - "codepage compiler option [C#]"
  - "-codepage compiler option [C#]"
ms.assetid: 75942989-b69a-4308-90a0-840c73d2c478
caps.latest.revision: 15
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# /codepage (C# Compiler Options)
Esta opción especifica qué página de códigos se debe utilizar durante la compilación si la página necesaria no es la predeterminada para el sistema en ese momento.  
  
## Sintaxis  
  
```  
/codepage:id  
```  
  
## Argumentos  
 `id`  
 Identificador de la página de códigos para todos los archivos de código fuente en la compilación.  
  
## Comentarios  
 Si se compilan uno o varios archivos de código fuente que no se crearon para utilizar la página de códigos predeterminada en el equipo, se podrá utilizar la opción **\/codepage** para especificar la página de códigos que se debe utilizar.  **\/codepage** se aplica a todos los archivos de código fuente de la compilación.  
  
 Si los archivos de código fuente se crearon con la misma página de códigos que está activada en el equipo o se crearon con UNICODE o UTF\-8, no es preciso utilizar **\/codepage**.  
  
 Vea [GetCPInfo](http://go.microsoft.com/fwlink/?LinkId=148371) para obtener información sobre cómo buscar las páginas de códigos se admiten en el sistema.  
  
 Esta opción del compilador no está disponible en Visual Studio y no se puede cambiar mediante programación.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)