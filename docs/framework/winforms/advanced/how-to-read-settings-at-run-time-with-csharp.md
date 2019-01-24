---
title: Cómo Leer la configuración en tiempo de ejecución conC#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d798b40e5e337ea7652c8e82cb7fa860a87528b9
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54521756"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Cómo Leer la configuración en tiempo de ejecución conC# #
Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties. El objeto Properties expone todos los valores de configuración predeterminados para el proyecto a través del miembro Properties.Settings.Default.  
  
### <a name="to-read-settings-at-run-time-with-c"></a>Para leer valores de configuración en tiempo de ejecución con C#  
  
-   Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default.  En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor. Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`. Para obtener información acerca de cómo crear un archivo de configuración, consulte [How To: Crear una nueva configuración en tiempo de diseño](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a>Vea también
- [Utilizar valores de configuración de aplicación y de usuario](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)
- [Cómo: Escribir la configuración de usuario en tiempo de ejecución conC#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)
- [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
