---
title: "Leer y escribir en el Registro (Visual Basic) | Microsoft Docs"
ms.custom: ""
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
  - "My.Computer.Registry (objeto), tareas"
  - "Registro, leer"
  - "Registro, escribir"
ms.assetid: a13da106-185b-41d7-b23c-416da65e21e4
caps.latest.revision: 21
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 21
---
# Leer y escribir en el Registro (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Este tema describe tarea y temas conceptuales que son asociado al registro.  
  
 Al programar en [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)], puede optar por obtener acceso al Registro a través de las funciones proporcionadas por [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] o a través de las clases de Registro de .NET Framework.  El Registro hospeda información del sistema operativo, así como de las aplicaciones que se encuentran en el equipo.  Al trabajar con el Registro se puede comprometer la seguridad, al permitir accesos inadecuados a recursos del sistema o a información reservada.  
  
## En esta sección  
 [Cómo: Crear una clave del Registro y establecer su valor](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-create-a-registry-key-and-set-its-value.md)  
 Describe cómo utilizar los métodos de `CreateSubKey` y de `SetValue` del objeto de `My.Computer.Registry` para crear una clave del Registro y establecer su valor.  
  
 [Cómo: Leer un valor a partir de una clave del Registro](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-read-a-value-from-a-registry-key.md)  
 Describe cómo utilizar el método de `GetValue` del objeto de `My.Computer.Registry` para leer un valor de una clave del Registro.  
  
 [Cómo: Eliminar una clave del Registro](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-delete-a-registry-key.md)  
 Describe cómo utilizar el método de `DeleteSubKey` de la propiedad de `My.Computer.Registry.CurrentUser` para eliminar una clave del Registro.  
  
 [Leer y escribir en el Registro mediante Microsoft.Win32 Namespace](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry-using-the-microsoft-win32-namespace.md)  
 Describe cómo utilizar las clases de `Registry` y de `RegistryKey` de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort-md.md)] para tener acceso al registro.  
  
 [Seguridad y Registro](../../../../visual-basic/developing-apps/programming/computer-resources/security-and-the-registry.md)  
 Aborda problemas de seguridad que implican al Registro.  
  
## Secciones relacionadas  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 Muestra y explica los miembros del objeto `My.Computer.Registry`.  
  
 <xref:Microsoft.Win32.Registry>  
 Presenta información general sobre la clase `Registry` junto con vínculos a claves y miembros individuales.