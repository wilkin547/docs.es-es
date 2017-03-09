---
title: "Error al crear manifiesto del ensamblado: &lt;mensaje de error&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc30140"
  - "vbc30140"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30140"
ms.assetid: 1beb5aa0-7b79-4c85-946b-5c2d0a41d1d2
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Error al crear manifiesto del ensamblado: &lt;mensaje de error&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] llama a Assembly Linker \(Al.exe, también denominado Alink\) para generar un ensamblado con un manifiesto.  El vinculador ha informado de un error en una fase previa a la emisión de la creación del ensamblado.  
  
 Esto puede suceder si existen problemas con el archivo de clave o el contenedor de claves especificado.  Para firmar completamente un ensamblado, debe proporcionar un archivo de clave válido que contenga información sobre las claves pública y privada.  Para retrasar la firma de un ensamblado, debe activar la casilla **Retrasar solo firma** y proporcionar un archivo de clave válido que contenga información sobre la clave pública.  La clave privada no es necesaria cuando un ensamblado tiene la firma retrasada.  Para obtener más información, vea [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/es-es/f468a7d3-234c-4353-924d-8e0ae5896564).  
  
 **Identificador del error:** BC30140  
  
### Para corregir este error  
  
1.  Estudie el mensaje de error citado y busque el error AL1019 en el tema [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/es-es/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) para ver una explicación más detallada y consejos.  
  
2.  Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
## Vea también  
 [How to: Sign an Assembly \(Visual Studio\)](http://msdn.microsoft.com/es-es/f468a7d3-234c-4353-924d-8e0ae5896564)   
 [Página Firma, Diseñador de proyectos](/visual-studio/ide/reference/signing-page-project-designer)   
 [Al.exe \(Assembly Linker\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/es-es/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Hable con nosotros](/visual-studio/ide/talk-to-us)