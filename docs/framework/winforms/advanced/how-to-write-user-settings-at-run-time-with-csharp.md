---
title: Cómo escribir valores de configuración de usuario en tiempo de ejecución con C#
description: Obtenga información sobre cómo escribir valores de configuración en tiempo de ejecución con C# conservando los cambios en la configuración entre sesiones de aplicación llamando al método Save.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], run time
- application settings [Windows Forms], writing user settings
- application settings [Windows Forms], C#
ms.assetid: 9d061c7d-b33b-470f-a36d-edccb1d6f9a3
ms.openlocfilehash: 6154ff1b92d6c2d4c788299e59eb8f73e6b69c4b
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84904330"
---
# <a name="how-to-write-user-settings-at-run-time-with-c"></a>Cómo: escribir la configuración de usuario en tiempo de ejecución con C\#

La configuración del ámbito de aplicación es de solo lectura y únicamente se puede cambiar en tiempo de diseño o modificando el archivo .config entre sesiones de aplicación. Sin embargo, la configuración del ámbito de usuario puede escribirse en tiempo de ejecución, del mismo modo que cambiaría cualquier valor de propiedad. El nuevo valor se conserva a lo largo de toda la sesión de la aplicación. Puede conservar los cambios de la configuración entre sesiones de aplicación llamando al método Save.  
  
## <a name="how-to-write-and-persist-user-settings-at-run-time-with-c"></a>Cómo: escribir y conservar la configuración de usuario en tiempo de ejecución con C\#
  
1. Acceda a la configuración y asigne un nuevo valor, tal como se muestra en este ejemplo:  
  
   ```csharp
   Properties.Settings.Default.myColor = Color.AliceBlue;  
   ```  
  
2. Si desea conservar los cambios de la configuración entre sesiones de aplicación, llame al método Save tal como se muestra en este ejemplo:  
  
    ```csharp
    Properties.Settings.Default.Save();  
    ```  
  
La configuración de usuario se guarda en un archivo en una subcarpeta de la carpeta de datos de aplicación oculta local del usuario.  
  
## <a name="see-also"></a>Consulte también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Cómo leer valores de configuración en tiempo de ejecución con C#](how-to-read-settings-at-run-time-with-csharp.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
