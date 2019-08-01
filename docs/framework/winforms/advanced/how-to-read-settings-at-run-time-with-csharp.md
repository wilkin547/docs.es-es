---
title: Cómo leer valores de configuración en tiempo de ejecución con C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 6a40718d57fad4041eeea2fded03b7256abbe8d1
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710227"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Cómo Leer la configuración en tiempo de ejecución con C\#

Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties. El objeto Properties expone todas las opciones de configuración predeterminadas del proyecto a través del miembro Properties. Settings. default en el espacio de nombres predeterminado del proyecto en el que se definen.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Para leer la configuración en tiempo de ejecución con C\#
  
Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default. En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor. Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`. Para obtener información acerca de cómo crear un archivo [de configuración, consulte Cómo: Cree un nuevo valor de configuración en](how-to-create-a-new-setting-at-design-time.md)tiempo de diseño.  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Vea también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Cómo: Escribir la configuración de usuario en tiempo de ejecución conC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
