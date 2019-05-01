---
title: Cómo leer valores de configuración en tiempo de ejecución con C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: 8cdc1a79f1ab327ae037cd6a04aa769196405127
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966937"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Cómo Leer la configuración en tiempo de ejecución con c#\#

Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties. El objeto Properties expone todos los valores de configuración predeterminados para el proyecto a través del miembro Properties.Settings.Default.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Para leer los valores en tiempo de ejecución con c#\#
  
Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default.  En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor. Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`. Para obtener información acerca de cómo crear un archivo de configuración, consulte [How To: Crear una nueva configuración en tiempo de diseño](how-to-create-a-new-setting-at-design-time.md).  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Vea también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Cómo: Escribir la configuración de usuario en tiempo de ejecución conC#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
