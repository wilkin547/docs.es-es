---
title: Cómo agregar varios conjuntos de valores de configuración a una aplicación en C#
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], multiple sets
- application settings [Windows Forms], C#
ms.assetid: 45007ac6-cf07-4be7-bc38-3f0ef962faf9
ms.openlocfilehash: c6842d11c04e905d42734af939f2c3f0cfeacd47
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040125"
---
# <a name="how-to-add-multiple-sets-of-settings-to-your-application-in-c"></a>Cómo Agregar varios conjuntos de valores de configuración a la aplicación en C\#

En algunos casos, es posible que desee tener varios conjuntos de valores de configuración en una aplicación. Por ejemplo, si está desarrollando una aplicación en la que se espera que un grupo determinado de valores de configuración cambie con frecuencia, puede ser aconsejable separarlos en un único archivo para que el archivo se pueda reemplazar de forma mayorista y no afecte a otros valores de configuración. Visual Studio permite agregar varios conjuntos de valores de configuración al proyecto. Se puede obtener acceso a conjuntos de configuración adicionales a `Properties.Settings` través del objeto.

## <a name="add-an-additional-set-of-settings"></a>Agregar un conjunto de valores adicional

1. En Visual Studio, en el menú **proyecto** , elija **Agregar nuevo elemento**.

   Se abre el cuadro de diálogo **Agregar nuevo elemento**.

2. En el cuadro de diálogo **Agregar nuevo elemento** , seleccione **archivo de configuración**, escriba un nombre para el archivo y haga clic en **Agregar** para agregar un nuevo archivo de configuración a la solución.

3. En **Explorador de soluciones**, arrastre el nuevo archivo de configuración a la carpeta **propiedades** . Esto permite que la nueva configuración esté disponible en el código.

4. Agregue y use la configuración de este archivo como lo haría con cualquier otro archivo de configuración. Puede tener acceso a este grupo de configuración a `Properties.Settings` través del objeto.

## <a name="see-also"></a>Vea también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
