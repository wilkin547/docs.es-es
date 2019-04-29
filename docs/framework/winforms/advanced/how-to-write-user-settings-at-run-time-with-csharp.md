---
title: Cómo escribir valores de configuración de usuario en tiempo de ejecución con C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 264fa9706f9255d7324cad6d02c36cc424e28995
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61778838"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Cómo Escribir la configuración de usuario en tiempo de ejecución con c#\#

La configuración del ámbito de aplicación es de solo lectura y únicamente se puede cambiar en tiempo de diseño o modificando el archivo .config entre sesiones de aplicación. Sin embargo, la configuración del ámbito de usuario puede escribirse en tiempo de ejecución, del mismo modo que cambiaría cualquier valor de propiedad. El nuevo valor se conserva a lo largo de toda la sesión de la aplicación. Puede conservar los cambios de la configuración entre sesiones de aplicación llamando al método Save.  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Cómo Escribir y mantener la configuración de usuario en tiempo de ejecución con c#\#
  
1. Acceda a la configuración y asigne un nuevo valor, tal como se muestra en este ejemplo:  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. Si desea conservar los cambios de la configuración entre sesiones de aplicación, llame al método Save tal como se muestra en este ejemplo:  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
La configuración de usuario se guarda en un archivo en una subcarpeta de la carpeta de datos de aplicación oculta local del usuario.  
  
## <a name="see-also"></a>Vea también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Cómo: Leer la configuración en tiempo de ejecución conC#](how-to-read-settings-at-run-time-with-csharp.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
