---
title: 'Cómo: Agregar varios conjuntos de valores de configuración a una aplicación en C#'
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: 029dffc878c62613e291620a2bd86971f369d15a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33520814"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Cómo: Agregar varios conjuntos de valores de configuración a una aplicación en C# #
En algunos casos, puede tener varios conjuntos de configuración en una aplicación. Por ejemplo, si está desarrollando una aplicación donde se espera un determinado grupo de valores que cambian con frecuencia, podría ser conveniente separarlos todos en un único archivo para que el archivo se puede reemplazar en su totalidad, no se ve afectada otros valores de configuración. Visual Studio permite agregar varios conjuntos de configuración para el proyecto. Pueden tener acceso a conjuntos adicionales de configuración a través del objeto Properties.Settings.  
  
### <a name="to-add-an-additional-set-of-setting-to-your-application"></a>Para agregar un conjunto adicional de configuración a la aplicación  
  
1.  En el menú **Proyecto** , elija **Agregar nuevo elemento**. Se abrirá el cuadro de diálogo **Agregar nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, seleccione **archivo de configuración de**, escriba un nombre para el archivo y haga clic en **agregar** para agregar un nuevo archivo de configuración a la solución.  
  
3.  En **el Explorador de soluciones**, arrastre el nuevo archivo de configuración en el **propiedades** carpeta. Esto permite que la nueva configuración esté disponible en el código.  
  
4.  Agregar y usar la configuración de este archivo como haría con cualquier otro archivo de configuración. Puede tener acceso a este grupo de configuración a través del objeto Properties.Settings.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar valores de configuración de aplicación y de usuario](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)
