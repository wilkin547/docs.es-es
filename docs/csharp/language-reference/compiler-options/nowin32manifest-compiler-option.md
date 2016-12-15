---
title: "/nowin32manifest (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/nowin32manifest"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "nowin32manifest compiler option [C#]"
  - "-nowin32manifest compiler option [C#]"
  - "/nowin32manifest compiler option [C#]"
ms.assetid: 6f06365b-b87b-46a2-b187-b3bfeaf4862d
caps.latest.revision: 15
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /nowin32manifest (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Utilice la opción **\/nowin32manifest** para indicar al compilador que no incruste ningún manifiesto de aplicación en el archivo ejecutable.  
  
## Sintaxis  
  
```  
/nowin32manifest  
```  
  
## Comentarios  
 Cuando se usa esta opción, la aplicación se someterá a la virtualización en Windows Vista, a menos que se proporcione un manifiesto de aplicación en un archivo de recursos Win32 o durante un paso de compilación posterior.  Para obtener más información sobre la virtualización, vea [New UAC Technologies for Windows Vista](http://msdn.microsoft.com/es-es/80efa4c7-3904-45c5-82e8-2d558fe67db9).  
  
 En Visual Studio, establezca esta opción en la página de **propiedades de la aplicación** seleccionando la opción **Crear aplicación sin manifiesto** en la lista desplegable **Manifiesto**.  Para obtener más información, vea [Página de aplicación, Diseñador de proyectos \(C\#\)](/visual-studio/ide/reference/application-page-project-designer-csharp).  
  
 Para obtener más información sobre la creación de manifiestos, vea [\/win32manifest \(Import a Custom Win32 Manifest File\)](../../../csharp/language-reference/compiler-options/win32manifest-compiler-option.md).  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)