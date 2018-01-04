---
title: "Dibujo y representación personalizados de controles"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 355a5842348aa4395d1841d0343080ddef634456
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="custom-control-painting-and-rendering"></a>Dibujo y representación personalizados de controles
Dibujo personalizado de controles es una de las muchas tareas complicadas facilitan por .NET Framework. Al crear un control personalizado, se tienen muchas opciones con respecto a la apariencia del control gráfica. Si va a crear un control que hereda de la `Control`, deberá proporcionar código que permita al control crear su representación gráfica. Si está creando un control de usuario mediante la herencia de la `UserControl`, o está heredando de uno de los controles de formularios Windows Forms, puede reemplazar la representación gráfica estándar y proporcionar su propio código de gráficos. Si desea proporcionar una representación personalizada para los controles constituyentes de una `UserControl` está creando, las opciones estarán mas limitadas, pero seguirá permitan a una amplia gama de posibilidades gráficas para los controles y aplicaciones.  
  
## <a name="in-this-section"></a>En esta sección  
 [Representar un control de formularios Windows Forms](../../../../docs/framework/winforms/controls/rendering-a-windows-forms-control.md)  
 Muestra cómo programar la lógica que muestra un control.  
  
 [Controles dibujados por el usuario](../../../../docs/framework/winforms/controls/user-drawn-controls.md)  
 Ofrezca una visión general de los pasos necesarios para escribir y reemplazar código de representación para el control.  
  
 [Controles constituyentes](../../../../docs/framework/winforms/controls/constituent-controls.md)  
 Describe cómo implementar código de representación personalizadas para los controles constituyentes en los formularios y los controles de usuario.  
  
 [Hacer un control no visible en tiempo de ejecución](../../../../docs/framework/winforms/controls/how-to-make-your-control-invisible-at-run-time.md)  
 Muestra cómo utilizar el <xref:System.Windows.Forms.Control.Visible%2A> propiedad para ocultar y mostrar un control.  
  
 [Proporcionar un fondo transparente a un control](../../../../docs/framework/winforms/controls/how-to-give-your-control-a-transparent-background.md)  
 Muestra cómo utilizar el <xref:System.Windows.Forms.Control.SetStyle%2A> método para crear un color de fondo opaco, transparente o parcialmente transparente.  
  
 [Representar controles con estilos visuales](../../../../docs/framework/winforms/controls/rendering-controls-with-visual-styles.md)  
 Muestra cómo representar controles con estilos visuales en los sistemas operativos que las admiten.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Control>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.UserControl>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Describe este método.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Crear objetos Graphics para dibujar](../../../../docs/framework/winforms/advanced/how-to-create-graphics-objects-for-drawing.md)  
 Presenta [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funcionalidad de gráficos de una perspectiva y proporciona vínculos a Visual Studio para obtener más información.  
  
 [Variedades de controles personalizados](../../../../docs/framework/winforms/controls/varieties-of-custom-controls.md)  
 Describe los tipos de controles personalizados que puede crear.
