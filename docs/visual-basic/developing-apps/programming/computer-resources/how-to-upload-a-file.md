---
description: 'Más información acerca de: Procedimiento: para cargar un archivo en Visual Basic'
title: Procedimiento para cargar un archivo
ms.date: 07/20/2015
helpviewer_keywords:
- networks, uploading files
- files [Visual Basic], uploading
- uploading files [Visual Basic]
- UploadFile method [Visual Basic]
- My.Computer.Network.UploadFile method
ms.assetid: a8b37924-c523-4fd3-b5ca-cb0074df29cd
ms.openlocfilehash: d38820cda6a143cf3f06bf6a2ca72cba5a9f3aef
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99675408"
---
# <a name="how-to-upload-a-file-in-visual-basic"></a>Cómo: Cargar un archivo en Visual Basic

El método <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A> se puede usar para cargar un archivo y almacenarlo en una ubicación remota. Si el parámetro `ShowUI` se establece en `True`, aparece un cuadro de diálogo que muestra el progreso de la carga y permite a los usuarios cancelar la operación.  
  
### <a name="to-upload-a-file"></a>Para cargar un archivo  
  
- Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un identificador uniforme de recursos (URI). En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`.  
  
     [!code-vb[VbResourceTasks#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#6)]  
  
### <a name="to-upload-a-file-and-show-the-progress-of-the-operation"></a>Para cargar un archivo y mostrar el progreso de la operación  
  
- Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un URI. En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx` sin indicar un nombre de usuario ni contraseña, se muestra el progreso de la carga y se cuenta con un intervalo de tiempo de espera de 500 milisegundos.  
  
     [!code-vb[VbResourceTasks#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#7)]  
  
### <a name="to-upload-a-file-supplying-a-user-name-and-password"></a>Para cargar un archivo, proporcionando un nombre de usuario y contraseña  
  
- Use el método `UploadFile` para cargar un archivo; especifique la ubicación del archivo de código fuente y la ubicación del directorio de destino como una cadena o un URI e indique el nombre de usuario y la contraseña. En este ejemplo se carga el archivo `Order.txt` en `http://www.cohowinery.com/uploads.aspx`, proporcionando el nombre de usuario `anonymous` y una contraseña en blanco.  
  
     [!code-vb[VbResourceTasks#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#8)]  
  
## <a name="robust-programming"></a>Programación sólida  

 Las siguientes condiciones pueden provocar una excepción:  
  
- La ruta de acceso de archivo local no es válida (<xref:System.ArgumentException>).  
  
- Error de autenticación (<xref:System.Security.SecurityException>).  
  
- Se agotó el tiempo de espera de la conexión (<xref:System.TimeoutException>).  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Network?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Devices.Network.UploadFile%2A>
- [Procedimiento para descargar un archivo](how-to-download-a-file.md)
- [Procedimiento para analizar rutas de acceso a archivos](../drives-directories-files/how-to-parse-file-paths.md)
