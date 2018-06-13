---
title: 'Cómo: Leer valores de configuración en tiempo de ejecución con C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8259e2f429718793c01868855651d1000620fae5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33521019"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Cómo: Leer valores de configuración en tiempo de ejecución con C# #
Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties. El objeto Properties expone todos los valores de configuración predeterminados para el proyecto a través del miembro Properties.Settings.Default.  
  
### <a name="to-read-settings-at-run-time-with-c"></a>Para leer valores de configuración en tiempo de ejecución con C#  
  
-   Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default.  En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor. Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`. Para obtener información acerca de cómo crear un archivo de configuración, consulte [Cómo: crear una nueva configuración en tiempo de diseño](../../../../docs/framework/winforms/advanced/how-to-create-a-new-setting-at-design-time.md).  
  
    ```  
    // C#  
    this.BackColor = Properties.Settings.Default.myColor;  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Utilizar valores de configuración de aplicación y de usuario](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Escribir valores de configuración de usuario en tiempo de ejecución con C#](../../../../docs/framework/winforms/advanced/how-to-write-user-settings-at-run-time-with-csharp.md)  
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
