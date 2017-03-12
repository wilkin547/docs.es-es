---
title: "C&#243;mo: Utilizar el espacio de nombres My (Gu&#237;a de programaci&#243;n de C#) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "lenguaje C#, acceso al espacio de nombres My"
ms.assetid: e7152414-0ea5-4c8e-bf02-c8d5bbe45ff4
caps.latest.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 12
---
# C&#243;mo: Utilizar el espacio de nombres My (Gu&#237;a de programaci&#243;n de C#)
El espacio de nombres <xref:Microsoft.VisualBasic.MyServices> \(`My` en Visual Basic\) proporciona acceso fácil e intuitivo a varias clases de .NET Framework, lo que permite escribir código que interactúe con el equipo, aplicación, configuración, recursos, etc.  Aunque originalmente se diseñó para el uso con Visual Basic, el espacio de nombres `MyServices` se puede utilizar en aplicaciones de C\#.  
  
 Para obtener más información sobre cómo utilizar el espacio de nombres `MyServices` de Visual Basic, vea [Desarrollo con la función My](../../../visual-basic/developing-apps/development-with-my/index.md).  
  
## Agregar una referencia  
 Antes de poder utilizar las clases `MyServices` en la solución, debe agregar una referencia a la biblioteca de Visual Basic.  
  
#### Para agregar una referencia a la biblioteca de Visual Basic  
  
1.  En el **Explorador de soluciones**, haga clic con el botón secundario del mouse en el nodo **Referencias** y seleccione **Agregar referencia**.  
  
2.  Cuando aparezca el cuadro de diálogo **Referencias**, desplácese por la lista y seleccione Microsoft.VisualBasic.dll.  
  
     También puede incluir la línea siguiente en la sección `using` al inicio del programa.  
  
     [!code-cs[csProgGuideNamespaces#18](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#18)]  
  
## Ejemplo  
 Este ejemplo llama a distintos métodos estáticos contenidos en el espacio de nombres `MyServices`.  Para que este código se compile, es necesario agregar al proyecto una referencia a Microsoft.VisualBasic.DLL.  
  
 [!code-cs[csProgGuideNamespaces#19](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#19)]  
  
 No todas las clases del espacio de nombres `MyServices` se pueden llamar desde una aplicación de C\#: por ejemplo, la clase <xref:Microsoft.VisualBasic.MyServices.FileSystemProxy> no es compatible.  En este caso particular, en lugar de esta clase se pueden utilizar los métodos estáticos que forman parte de <xref:Microsoft.VisualBasic.FileIO.FileSystem>, que también se encuentran en el archivo VisualBasic.dll.  Por ejemplo, aquí se muestra cómo utilizar un método de este tipo para duplicar un directorio:  
  
 [!code-cs[csProgGuideNamespaces#20](../../../csharp/programming-guide/namespaces/codesnippet/csharp/Namespaces/Namespaces3.cs#20)]  
  
## Vea también  
 [Guía de programación de C\#](../../../csharp/programming-guide/index.md)   
 [Espacios de nombres](../../../csharp/programming-guide/namespaces/index.md)   
 [Utilizar espacios de nombres](../../../csharp/programming-guide/namespaces/using-namespaces.md)