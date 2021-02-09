---
description: 'Más información acerca de: Procedimiento: para descargar un archivo en Visual Basic'
title: Procedimiento para descargar un archivo
ms.date: 07/20/2015
helpviewer_keywords:
- downloading Internet resources [Visual Basic], files
- downloading files [Visual Basic]
- remote computers [Visual Basic], downloading from
- files [Visual Basic], downloading
- files [Visual Basic], transferring
ms.assetid: ac479f81-c0e2-4b99-af73-217f446b73da
ms.openlocfilehash: dd296a5958431b74ccc8e0fb41a49073f4847ded
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797697"
---
# <a name="how-to-download-a-file-in-visual-basic"></a>Cómo: Descargar un archivo en Visual Basic

El método <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A> se puede usar para descargar un archivo remoto y almacenarlo en una ubicación específica. Si el parámetro `ShowUI` se establece en `True`, se abre un cuadro de diálogo que muestra el progreso de la descarga y permite a los usuarios cancelar la operación. De forma predeterminada, no se sobrescriben los archivos existentes que tengan el mismo nombre. Si quiere sobrescribir los archivos existentes, establezca el parámetro `overwrite` en `True`.

Las condiciones siguientes pueden provocar una excepción:

- El nombre de unidad no es válido (<xref:System.ArgumentException>).

- No se ha proporcionado la autenticación necesaria (<xref:System.UnauthorizedAccessException> o <xref:System.Security.SecurityException>).

- El servidor no responde en el `connectionTimeout` especificado (<xref:System.TimeoutException>).

- El sitio web ha denegado la solicitud (<xref:System.Net.WebException>).

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

> [!IMPORTANT]
> No tome ninguna decisión sobre el contenido del archivo basándose en su nombre. Por ejemplo, es posible que el archivo Form1.vb no sea un archivo de código fuente de Visual Basic. Compruebe todas las entradas antes de utilizar los datos en la aplicación. Puede que el contenido del archivo no sea el esperado y que los métodos que leen el archivo produzcan un error.

### <a name="to-download-a-file"></a>Para descargar un archivo

- Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo. En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`:

  [!code-vb[VbResourceTasks#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#9)]

### <a name="to-download-a-file-specifying-a-time-out-interval"></a>Para descargar un archivo, especificando un intervalo de tiempo de espera

- Use el método `DownloadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, la ubicación en la que se va a almacenar el archivo y el intervalo de tiempo de espera en milisegundos (el valor predeterminado es 1000). En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, especificando un intervalo de tiempo de espera de 500 milisegundos:

  [!code-vb[VbResourceTasks#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#10)]

### <a name="to-download-a-file-supplying-a-user-name-and-password"></a>Para descargar un archivo, proporcionando un nombre de usuario y contraseña

- Use el método `DownLoadFile` para descargar el archivo, especificando la ubicación del archivo de destino como una cadena o un identificador URI, y la ubicación en la que se va a almacenar el archivo, el nombre de usuario y la contraseña. En este ejemplo se descarga el archivo `WineList.txt` de `http://www.cohowinery.com/downloads` y se guarda en `C:\Documents and Settings\All Users\Documents`, con el nombre de usuario `anonymous` y una contraseña en blanco.

  [!code-vb[VbResourceTasks#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#11)]

  > [!IMPORTANT]
  > El protocolo FTP que usa el método `DownLoadFile` envía información, incluidas las contraseñas, en texto sin formato y no debe usarse para transmitir información confidencial.

## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Devices.Network>
- <xref:Microsoft.VisualBasic.Devices.Network.DownloadFile%2A>
- [Procedimiento para cargar un archivo](how-to-upload-a-file.md)
- [Procedimiento para analizar rutas de acceso a archivos](../drives-directories-files/how-to-parse-file-paths.md)
