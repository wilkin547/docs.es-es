---
title: "/delaysign (C# Compiler Options) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/delaysign"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "-delaysign compiler option [C#]"
  - "delaysign compiler option [C#]"
  - "/delaysign compiler option [C#]"
ms.assetid: bcb058eb-2933-4e7f-b356-5c941db4de75
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# /delaysign (C# Compiler Options)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Esta opción hace que el compilador reserve espacio en el archivo de salida de manera que se pueda agregar una firma digital más adelante.  
  
## Sintaxis  
  
```  
/delaysign[ + | - ]  
```  
  
## Argumentos  
 `+` &#124; `-`  
 Use **\/delaysign\-** para firmar completamente un ensamblado.  Utilice **\/delaysign\+** si desea incluir sólo la clave pública en el ensamblado.  El valor predeterminado es **\/delaysign\-**.  
  
## Comentarios  
 La opción **\/delaysign** no produce ningún efecto a menos que se utilice con [\/keyfile](../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md) o [\/keycontainer](../../../csharp/language-reference/compiler-options/keycontainer-compiler-option.md).  
  
 Cuando se solicita un ensamblado con firma completa, el compilador calcula el hash del archivo que contiene el manifiesto \(metadatos de ensamblado\) y firma el hash con la clave privada.  La firma digital resultante se almacena en el archivo que contiene el manifiesto.  Cuando se firma un ensamblado de forma retardada, el compilador no calcula ni almacena la firma, pero reserva espacio en el archivo para poder agregar la firma más tarde.  
  
 Por ejemplo, si se usa **\/delaysign\+**, los comprobadores podrán colocar el ensamblado en la caché global.  Después de las pruebas, se puede firmar totalmente el ensamblado colocando la clave privada en el mismo mediante la utilidad [Assembly Linker](../Topic/Al.exe%20\(Assembly%20Linker\).md).  
  
 Para obtener más información, vea [Crear y utilizar ensamblados con nombre seguro](../Topic/Creating%20and%20Using%20Strong-Named%20Assemblies.md) y [Retrasar la firma de un ensamblado](../Topic/Delay%20Signing%20an%20Assembly.md).  
  
### Para establecer esta opción del compilador en el entorno de desarrollo de Visual Studio  
  
1.  Abra la página **Propiedades** del proyecto.  
  
2.  Modifique la propiedad **Retrasar firma sólo**.  
  
 Para obtener información sobre cómo establecer esta opción del compilador mediante programación, vea <xref:VSLangProj80.ProjectProperties3.DelaySign%2A>.  
  
## Vea también  
 [C\# Compiler Options](../../../csharp/language-reference/compiler-options/index.md)   
 [Cómo: Modificar las propiedades y los valores de configuración del proyecto](http://msdn.microsoft.com/es-es/e7184bc5-2f2b-4b4f-aa9a-3ecfcbc48b67)