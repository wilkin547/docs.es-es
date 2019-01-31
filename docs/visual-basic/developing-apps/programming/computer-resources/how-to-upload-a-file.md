---
title: Procedimiento para cargar un archivo en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: 0d0aaca06a72b9bd2631a652a0b4756f4681df7d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54704412"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a>Procedimiento para cargar un archivo en Visual Basic
El método <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> se puede usar para cargar un archivo y almacenarlo en una ubicación remota. Si el parámetro `ShowUI` se establece en `True`, aparece un cuadro de diálogo que muestra el progreso de la carga y permite a los usuarios cancelar la operación.  
  
### <a name="to-upload-a-file"></a>Para cargar un archivo  
  
-   Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un identificador uniforme de recursos (URI). En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`.  
  
     [!code-vb[VbResourceTasks#6](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_1.vb)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a>Para cargar un archivo y mostrar el progreso de la operación  
  
-   Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un URI. En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx` sin indicar un nombre de usuario ni contraseña, se muestra el progreso de la carga y se cuenta con un intervalo de tiempo de espera de 500 milisegundos.  
  
     [!code-vb[VbResourceTasks#7](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_2.vb)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a>Para cargar un archivo, proporcionando un nombre de usuario y contraseña  
  
-   Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un URI e indique el nombre de usuario y la contraseña. En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`, proporcionando el nombre de usuario `anonymous` y una contraseña en blanco.  
  
     [!code-vb[VbResourceTasks#8](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-upload-a-file_3.vb)]  
  
## <a name="robust-programming"></a>Programación sólida  
 Las siguientes condiciones pueden provocar una excepción:  
  
-   La ruta de acceso de archivo local no es válida (<xref:System.ArgumentException>).  
  
-   Error de autenticación (<xref:System.Security.SecurityException>).  
  
-   Se agotó el tiempo de espera de la conexión (<xref:System.TimeoutException>).  
  
## <a name="see-also"></a>Vea también
- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [Cómo: Descargar un archivo](../../../../visual-basic/developing-apps/programming/computer-resources/how-to-download-a-file.md)
- [Cómo: Analizar rutas de acceso a archivos](../../../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
