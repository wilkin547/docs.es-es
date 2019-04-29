---
title: Cómo agregar varios conjuntos de valores de configuración a una aplicación en C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 9a4913f635204aac2214d97225c7b8147c6fe9ab
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61768555"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Cómo Agregar varios conjuntos de configuración de la aplicación en C\#
En algunos casos, puede tener varios conjuntos de configuración en una aplicación. Por ejemplo, si está desarrollando una aplicación donde se espera un determinado grupo de valores que cambian con frecuencia, sería conveniente separar todos en un único archivo para que se puede reemplazar el archivo de manera global, que no afecta a otras opciones. Visual Studio permite agregar varios conjuntos de configuración al proyecto. Pueden acceder a través del objeto Properties.Settings conjuntos adicionales de configuración.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>Para agregar un conjunto adicional de la configuración de la aplicación  
  
1. En el menú **Proyecto** , elija **Agregar nuevo elemento**. Se abre el cuadro de diálogo **Agregar nuevo elemento**.  
  
2. En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **archivoConfiguración**, escriba un nombre para el archivo y haga clic en **agregar** para agregar un nuevo archivo de configuración a la solución.  
  
3. En **el Explorador de soluciones**, arrastre el nuevo archivo de configuración en el **propiedades** carpeta. Esto permite que la nueva configuración esté disponible en el código.  
  
4. Agregar y usar la configuración de este archivo como lo haría con cualquier otro archivo de configuración. Puede tener acceso a este grupo de configuración a través del objeto Properties.Settings.  
  
## <a name="see-also"></a>Vea también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
