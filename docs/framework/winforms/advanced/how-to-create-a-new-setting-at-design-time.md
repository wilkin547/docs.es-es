---
title: Cómo crear un valor de configuración en tiempo de diseño
description: Obtenga información sobre cómo crear un nuevo Windows Forms valor en tiempo de diseño mediante el diseñador de configuración de Visual Studio.
ms.date: 03/30/2017
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
ms.openlocfilehash: ce37b42191999e29de2f2f7f7e7abfa0ec3f4d47
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325848"
---
# <a name="how-to-create-a-new-setting-at-design-time"></a>Cómo: crear un nuevo valor de configuración en tiempo de diseño

Puede crear un nuevo valor de configuración en tiempo de diseño mediante el diseñador de configuración de Visual Studio. El diseñador de configuración es una interfaz de estilo de cuadrícula que le permite crear nuevas opciones de configuración y especificar propiedades para esas opciones. Debe especificar el nombre, el valor, el tipo y el ámbito de la nueva configuración. Una vez creada la configuración, se puede acceder a ella en el código.

## <a name="create-a-new-setting-at-design-time-in-c"></a>Crear un nuevo valor de configuración en tiempo de diseño en C\#

1. Abra Visual Studio.

2. En **Explorador de soluciones**, expanda el nodo **propiedades** del proyecto.

3. Haga doble clic en el archivo. Settings en el que desea agregar un nuevo valor. El nombre predeterminado de este archivo es Settings. Settings.

4. En el diseñador de configuración, establezca el **nombre**, el **valor**, el **tipo**y el **ámbito** de la configuración. Cada fila representa una única configuración.

## <a name="create-a-new-setting-at-design-time-in-visual-basic"></a>Crear un nuevo valor de configuración en tiempo de diseño en Visual Basic

1. Abra Visual Studio.

2. En **Explorador de soluciones**, haga clic con el botón secundario en el nodo del proyecto y elija **propiedades**.

3. En la página **propiedades** , seleccione la pestaña **configuración** .

4. En el diseñador de configuración, establezca el **nombre**, el **valor**, el **tipo**y el **ámbito** de la configuración. Cada fila representa una única configuración.

## <a name="see-also"></a>Vea también

- [Utilizar valores de configuración de aplicación y de usuario](using-application-settings-and-user-settings.md)
- [Introducción a la configuración de la aplicación](application-settings-overview.md)
- [Cómo cambiar el valor de una opción de configuración existente en tiempo de diseño](how-to-change-the-value-of-an-existing-setting-at-design-time.md)
