---
title: "Cómo: Descargar un archivo en Visual Basic | Microsoft Docs"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- downloading Internet resources, files
- downloading files
- remote computers, downloading from
- files, downloading
- files, transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
caps.latest.revision: 22
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: bd37b52d12876dad6ec4b2a1bb34f4987f933c08
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-download-a-file-in-visual-basic"></a>Cómo: Descargar un archivo en Visual Basic
Se puede usar el método <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> para descargar un archivo remoto y almacenarlo en una ubicación específica. Si el parámetro `ShowUI` se establece en `True`, se abre un cuadro de diálogo que muestra el progreso de la descarga y permite a los usuarios cancelar la operación. De forma predeterminada, no se sobrescriben los archivos existentes que tengan el mismo nombre. Si quiere sobrescribir los archivos existentes, establezca el parámetro `overwrite` en `True`.  
  
 Las condiciones siguientes pueden provocar una excepción:  
  
-   El nombre de la unidad no es válido (<xref:System.ArgumentException>).  
  
-   No se proporcionó la autenticación necesaria (<xref:System.UnauthorizedAccessException> o <xref:System.Security.SecurityException>).  
  
-   El servidor no responde en el `connectionTimeout` especificado (<xref:System.TimeoutException>).  
  
-   El sitio web deniega la solicitud (<xref:System.Net.WebException>).  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
> [!IMPORTANT]
>  No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic. Compruebe todas las entradas antes de utilizar los datos en la aplicación. Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.  
  
### <a name="to-download-a-file"></a>Para descargar un archivo  
  
-   Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo. En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`:  
  
     [!code-vb[VbResourceTasks#9](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_1.vb)]  
  
### <a name="to-download-a-file-specifying-a-time-out-interval"></a>Para descargar un archivo, especificando un intervalo de tiempo de espera  
  
-   Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, la ubicación en la que se va a almacenar el archivo y el intervalo de tiempo de espera en milisegundos (el valor predeterminado es 1000). En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, especificando un intervalo de tiempo de espera de 500 milisegundos:  
  
     [!code-vb[VbResourceTasks#10](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_2.vb)]  
  
### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>Para descargar un archivo, proporcionando un nombre de usuario y contraseña  
  
-   Use el método `DownLoadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo, el nombre de usuario y la contraseña. En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, con el nombre de usuario `anonymous` y una contraseña en blanco.  
  
     [!code-vb[VbResourceTasks#11](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-download-a-file_3.vb)]  
  
    > [!IMPORTANT]
    >  El protocolo FTP que usa el método `DownLoadFile` envía información, incluidas las contraseñas, en texto sin formato y no debe usarse para transmitir información confidencial.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Devices.Network>   
 <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>   
 [Cómo: Cargar un archivo](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-upload-a-file.md)   
 [Analizar rutas de acceso a archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)

