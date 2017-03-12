---
title: "C&#243;mo: Escribir texto en archivos del directorio Mis documentos en Visual Basic | Microsoft Docs"
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
  - "ejemplos [Visual Basic], archivos de texto"
  - "archivos, escribir"
  - "texto, escribir en archivos"
  - "escribir en archivos, en Mis documentos"
ms.assetid: 1c726124-781d-4976-9baa-ed46814ff3fe
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 19
---
# C&#243;mo: Escribir texto en archivos del directorio Mis documentos en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El objeto `My.Computer.FileSystem.SpecialDirectories` permite tener acceso a los directorios especiales, como el directorio **MyDocuments**.  
  
## Procedimiento  
  
#### Para escribir nuevos archivos de texto en el directorio Mis documentos  
  
1.  Utilice la propiedad `My.Computer.FileSystem.SpecialDirectories.MyDocuments` para proporcionar la ruta de acceso.  
  
     [!code-vb[VbFileIOWrite#1](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-fil_1_1.vb)]  
  
2.  Utilice el método `WriteAllText` para escribir texto en el archivo especificado.  
  
     [!code-vb[VbVbcnMyFileSystem#14](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-fil_1_2.vb)]  
  
## Ejemplo  
 [!code-vb[VbFileIOWrite#2](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/visualbasic/how-to-write-text-to-fil_1_3.vb)]  
  
## Compilar el código  
 Reemplace `test.txt` con el nombre del archivo en el que desea escribir.  
  
## Programación eficaz  
 Este código vuelve a producir todas las excepciones que pueden ocurrir al escribir texto en el archivo.  Puede reducir la probabilidad de que se produzcan excepciones utilizando los controles de formularios Windows Forms como los componentes [OpenFileDialog](../Topic/OpenFileDialog%20Component%20\(Windows%20Forms\).md) y [SaveFileDialog](../Topic/SaveFileDialog%20Component%20\(Windows%20Forms\).md), que limitan las opciones del usuario a los nombres de archivo válidos.  No obstante, el uso de estos controles no es infalible.  El sistema de archivos puede cambiar entre el momento en el que el usuario selecciona un archivo y el momento en el que se ejecuta el código.  Por ello, cuando se trabaja con archivos casi siempre es prácticamente obligatorio realizar un control de excepciones.  
  
## Seguridad de .NET Framework  
 Si realiza una ejecución en un contexto de confianza parcial, el código podría desencadenar una excepción por falta de privilegios.  Para obtener más información, vea [Code Access Security Basics](../Topic/Code%20Access%20Security%20Basics.md).  
  
 Este ejemplo crea un nuevo archivo.  Si una aplicación necesita crear un archivo, precisará permisos de creación para la carpeta correspondiente.  Los permisos se establecen usando listas de control de acceso.  Sin embargo, si el archivo ya existe, la aplicación sólo precisará permiso de escritura, un privilegio menor.  Por tanto, siempre que sea posible, resulta más seguro crear el archivo durante la implementación y conceder sólo privilegios de lectura en un solo archivo, en lugar de privilegios de creación para una carpeta.  También es más seguro escribir datos en carpetas de usuario en lugar de en la carpeta raíz o en la carpeta **Archivos de programa**.  Para obtener más información, vea [ACL Technology Overview](http://msdn.microsoft.com/es-es/06fbf66d-6f02-4378-b863-b2f12e349045).  
  
## Vea también  
 <xref:System.IO.Path.Combine%2A?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Computer>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem>   
 <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A>   
 <xref:Microsoft.VisualBasic.FileIO.SpecialDirectories>