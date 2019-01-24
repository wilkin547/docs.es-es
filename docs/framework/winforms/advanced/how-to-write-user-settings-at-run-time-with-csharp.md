---
title: Cómo Escribir la configuración de usuario en tiempo de ejecución conC#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: a62bf540ebdc383f26bd4aed760b2562437047aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560950"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Cómo Escribir la configuración de usuario en tiempo de ejecución conC# #
La configuración del ámbito de aplicación es de solo lectura y únicamente se puede cambiar en tiempo de diseño o modificando el archivo .config entre sesiones de aplicación. Sin embargo, la configuración del ámbito de usuario puede escribirse en tiempo de ejecución, del mismo modo que cambiaría cualquier valor de propiedad. El nuevo valor se conserva a lo largo de toda la sesión de la aplicación. Puede conservar los cambios de la configuración entre sesiones de aplicación llamando al método Save.  
  
### <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Cómo Escribir y mantener la configuración de usuario en tiempo de ejecución conC#  
  
1.  Acceda a la configuración y asigne un nuevo valor, tal como se muestra en este ejemplo:  
  
    ```  
    // C#  
    Properties.Settings.Default.myColor = Color.AliceBlue;  
    ```  
  
2.  Si desea conservar los cambios de la configuración entre sesiones de aplicación, llame al método Save tal como se muestra en este ejemplo:  
  
    ```  
    // C#  
    Properties.Settings.Default.Save();  
    ```  
  
     La configuración de usuario se guarda en un archivo en una subcarpeta de la carpeta de datos de aplicación oculta local del usuario.  
  
## <a name="see-also"></a>Vea también
- [Utilizar valores de configuración de aplicación y de usuario](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [Cómo: Leer la configuración en tiempo de ejecución conC#](../../../../docs/framework/winforms/advanced/how-to-read-settings-at-run-time-with-csharp.md)
- [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
