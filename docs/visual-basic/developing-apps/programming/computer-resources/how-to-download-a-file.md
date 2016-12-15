---
title: "C&#243;mo: Descargar un archivo en Visual Basic | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "descargar archivos"
  - "descargar recursos de Internet, archivos"
  - "archivos, descargar"
  - "archivos, transferir"
  - "equipos remotos, descargar de"
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# C&#243;mo: Descargar un archivo en Visual Basic
[!INCLUDE[vs2017banner](../../../../csharp/includes/vs2017banner.md)]

El método <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> se puede utilizar para descargar un archivo remoto y almacenarlo en una ubicación concreta.  Si el parámetro `ShowUI` se establece en `True`, aparece un cuadro de diálogo que muestra el progreso de la descarga y permite a los usuarios cancelar la operación.  De manera predeterminada, no se sobrescriben los archivos existentes que tienen el mismo nombre; si desea sobrescribir los archivos existentes, establezca el parámetro `overwrite` en `True`.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la unidad no es válido \(<xref:System.ArgumentException>\).  
  
-   No se ha proporcionado la autenticación necesaria \(<xref:System.UnauthorizedAccessException> o <xref:System.Security.SecurityException>\).  
  
-   El servidor no responde dentro del valor de `connectionTimeout` especificado \(<xref:System.TimeoutException>\).  
  
-   El sitio Web deniega la solicitud \(<xref:System.Net.WebException>\).  
  
 [!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
> [!IMPORTANT]
>  No tome ninguna decisión sobre el contenido del archivo basándose en su nombre.  Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic.  Compruebe todas las entradas antes de utilizar los datos en la aplicación.  Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
### Para descargar un archivo  
  
-   Utilice el método `DownloadFile` para descargar el archivo; especifique la ubicación del archivo de destino como una cadena o un identificador uniforme de recursos \(URI\) y la ubicación donde se va a almacenar el archivo.  En este ejemplo se descarga el archivo `WineList.txt` desde `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`:  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### Para descargar un archivo, especificando un intervalo de tiempo de espera  
  
-   Utilice el método `DownloadFile` para descargar el archivo; especifique la ubicación del archivo de destino como una cadena o un identificador uniforme de recursos \(URI\), la ubicación donde se va a almacenar el archivo y el intervalo de tiempo de espera en milisegundos \(el valor predeterminado es 1000\).  Este ejemplo descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y lo guarda en `C:\Documents and Settings\All Users\Documents`, especificando un intervalo de tiempo de espera de 500 milisegundos:  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### Para descargar un archivo, proporcionando un nombre de usuario y contraseña  
  
-   Utilice el método `DownLoadFile` para descargar el archivo; especifique la ubicación del archivo de destino como una cadena o un identificador uniforme de recursos \(URI\), la ubicación donde se va a almacenar el archivo, el nombre de usuario y la contraseña.  Este ejemplo descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y lo guarda en `C:\Documents and Settings\All Users\Documents`, con el nombre de usuario `anonymous` y una contraseña en blanco.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  El método `DownLoadFile` utiliza el protocolo FTP para enviar información, incluidas las contraseñas, en texto sin formato y no se debe utilizar para transmitir información confidencial.  
  
## Vea también  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [Cómo: Cargar un archivo](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [Cómo: Analizar rutas de acceso a archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)