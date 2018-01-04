---
title: "Cómo: Crear un nuevo valor de configuración en tiempo de diseño"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- application settings [Windows Forms], design time
- application settings [Windows Forms], creating
ms.assetid: c5d60a66-6507-462f-a81f-e3bc0a804e16
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 04b86579f45c5a357f8759bf36ae41f7a5c6e98b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-new-setting-at-design-time"></a>Cómo: Crear un nuevo valor de configuración en tiempo de diseño
Puede crear una nueva configuración en tiempo de diseño mediante el Diseñador de configuración. El Diseñador de configuración es una interfaz de estilo de cuadrícula que le permite crear una nueva configuración y especificar propiedades para ver esas configuraciones. Debe especificar el nombre, valor, tipo y ámbito de la nueva configuración. Una vez que se crea una configuración, es accesible en el código.  
  
### <a name="to-create-a-new-setting-at-design-time-in-c"></a>Para crear una nueva configuración en tiempo de diseño en C#  
  
1.  En **el Explorador de soluciones**, expanda la **propiedades** nodo del proyecto.  
  
2.  Haga doble clic en el archivo .settings en el que desea agregar una nueva configuración. El nombre predeterminado de este archivo es Settings.settings.  
  
3.  En el Diseñador de configuración, establezca el nombre, el valor, el tipo y el ámbito de la configuración. Cada fila representa un valor único.  
  
### <a name="to-create-a-new-setting-at-design-time-in-visual-basic"></a>Para crear una nueva configuración en tiempo de diseño en Visual Basic  
  
1.  En **el Explorador de soluciones**, haga clic en el nodo del proyecto y elija **propiedades**.  
  
2.  En el **propiedades** página, seleccione la **configuración** ficha.  
  
3.  En el Diseñador de configuración, establezca el nombre, el valor, el tipo y el ámbito de la configuración. Cada fila representa un valor único.  
  
## <a name="see-also"></a>Vea también  
 [Utilizar valores de configuración de aplicación y de usuario](../../../../docs/framework/winforms/advanced/using-application-settings-and-user-settings.md)  
 [Introducción a la configuración de la aplicación](../../../../docs/framework/winforms/advanced/application-settings-overview.md)  
 [Cambiar el valor de una opción de configuración existente en tiempo de diseño](../../../../docs/framework/winforms/advanced/how-to-change-the-value-of-an-existing-setting-at-design-time.md)
