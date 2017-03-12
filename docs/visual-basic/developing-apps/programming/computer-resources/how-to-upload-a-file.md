---
title: "C&#243;mo: Cargar un archivo en Visual Basic | Microsoft Docs"
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
  - "archivos, cargar"
  - "My.Computer.Network.UploadFile (método)"
  - "redes, cargar archivos"
  - "UploadFile (método)"
  - "cargar archivos"
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# C&#243;mo: Cargar un archivo en Visual Basic
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El método <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> se puede utilizar para cargar un archivo y almacenarlo en una ubicación remota.  Si el parámetro `ShowUI` se establece en `True`, aparece un cuadro de diálogo que muestra el progreso de la descarga y permite a los usuarios cancelar la operación.  
  
### Para cargar un archivo  
  
-   Utilice el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un identificador uniforme de recursos \(URI\). Este ejemplo carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`.  
  
     [!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-upload-a-file_1.vb)]  
  
### Para cargar un archivo y mostrar el progreso de la operación  
  
-   Utilice el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un identificador uniforme de recursos \(URI\).  Este ejemplo carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx` sin indicar un nombre de usuario ni contraseña, muestra el progreso de la carga y cuenta con un intervalo de tiempo de espera de 500 milisegundos.  
  
     [!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-upload-a-file_2.vb)]  
  
### Para cargar un archivo, proporcionando un nombre de usuario y contraseña  
  
-   Utilice el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un identificador uniforme de recursos \(URI\) e indique el nombre de usuario y la contraseña.  Este ejemplo carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`, proporcionando el nombre de usuario `anonymous` y una contraseña en blanco.  
  
     [!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/visualbasic/how-to-upload-a-file_3.vb)]  
  
## Programación eficaz  
 Las siguientes condiciones pueden provocar una excepción:  
  
-   La ruta de acceso al archivo local no es válida \(<xref:System.ArgumentException>\).  
  
-   Se produjo un error en la autenticación \(<xref:System.Security.SecurityException>\).  
  
-   Se agotó el tiempo de espera de la conexión \(<xref:System.TimeoutException>\).  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=fullName>   
 <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>   
 [Cómo: Descargar un archivo](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)   
 [Cómo: Analizar rutas de acceso a archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)