---
title: Cómo leer valores de configuración en tiempo de ejecución con C#
description: Obtenga información sobre cómo leer la configuración de ámbito de aplicación y de ámbito de usuario en tiempo de ejecución con C# a través del objeto de propiedades.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], reading
- application settings [Windows Forms], run time
- application settings [Windows Forms], C#
ms.assetid: dbe8bf09-5e1c-49da-9192-154033d7240b
ms.openlocfilehash: d784544e018bb693c501e35ea36fcae1946ef5eb
ms.sourcegitcommit: 3824ff187947572b274b9715b60c11269335c181
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2020
ms.locfileid: "84903361"
---
# <a name="how-to-read-settings-at-run-time-with-c"></a>Cómo: leer la configuración en tiempo de ejecución con C\#

Puede leer valores de configuración de aplicación y usuario en tiempo de ejecución a través del objeto Properties. El objeto Properties expone todas las opciones de configuración predeterminadas del proyecto a través del miembro Properties. Settings. default en el espacio de nombres predeterminado del proyecto en el que se definen.  
  
## <a name="to-read-settings-at-run-time-with-c"></a>Para leer la configuración en tiempo de ejecución con C\#
  
Acceda a la configuración correspondiente a través del miembro Properties.Settings.Default.  En el ejemplo siguiente, se muestra cómo asignar un valor de configuración con el nombre `myColor` a una propiedad BackColor. Es necesario que haya creado previamente un archivo de configuración con una configuración denominada `myColor` de tipo `System.Drawing.Color`. Para obtener información sobre cómo crear un archivo de configuración, vea [Cómo: crear un nuevo valor de configuración en tiempo de diseño](how-to-create-a-new-setting-at-design-time.md).  
  
```csharp
this.BackColor = Properties.Settings.Default.myColor;  
```  
  
## <a name="see-also"></a>Consulte también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Cómo escribir valores de configuración de usuario en tiempo de ejecución con C#](how-to-write-user-settings-at-run-time-with-csharp.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
