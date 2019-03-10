---
title: Dibujo y representación personalizados de controles
ms.date: 03/30/2017
helpviewer_keywords:
- custom controls [Windows Forms], rendering
- custom controls [Windows Forms], painting
- user controls [Windows Forms], painting
ms.assetid: a09dbf76-0966-4cbf-a66a-2083ba98e068
ms.openlocfilehash: ec9002ffa4a7e2c82f59d52344764a01afe4c568
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722144"
---
# <a name="custom-control-painting-and-rendering"></a>Dibujo y representación personalizados de controles
Dibujo personalizado de controles es una de las muchas tareas complicadas fáciles mediante .NET Framework. Al crear un control personalizado, tiene muchas opciones con respecto a la apariencia gráfica del control. Si va a crear un control que hereda de la `Control`, debe proporcionar código que permita el control representar su representación gráfica. Si va a crear un control de usuario que se herede de la `UserControl`, o se hereda desde uno de los controles de Windows Forms, puede reemplazar la representación gráfica estándar y proporcionar su propio código de gráficos. Si desea proporcionar una representación personalizada para los controles constituyentes de una `UserControl` va a crear, las opciones se convierten en más limitadas, pero aún permiten una amplia gama de posibilidades gráficas para los controles y las aplicaciones.  
  
## <a name="in-this-section"></a>En esta sección  
 [Representar un control de formularios Windows Forms](rendering-a-windows-forms-control.md)  
 Muestra cómo programar la lógica que muestra un control.  
  
 [Controles dibujados por el usuario](user-drawn-controls.md)  
 Proporciona información general de los pasos necesarios para escribir y reemplazar código de representación para el control.  
  
 [Controles constituyentes](constituent-controls.md)  
 Describe cómo implementar el código de representación personalizadas para controles constituyentes en los controles de usuario y los formularios.  
  
 [Cómo: Hacer que el Control Invisible en tiempo de ejecución](how-to-make-your-control-invisible-at-run-time.md)  
 Se muestra cómo usar el <xref:System.Windows.Forms.Control.Visible%2A> propiedad para ocultar y mostrar un control.  
  
 [Cómo: Proporcionar un fondo transparente a un Control](how-to-give-your-control-a-transparent-background.md)  
 Se muestra cómo usar el <xref:System.Windows.Forms.Control.SetStyle%2A> método para crear un color de fondo opaco, transparente o parcialmente transparentes.  
  
 [Representar controles con estilos visuales](rendering-controls-with-visual-styles.md)  
 Muestra cómo representar controles con estilos visuales en sistemas operativos compatibles con ellos.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Windows.Forms.Control>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.UserControl>  
 Describe esta clase y contiene vínculos a todos sus miembros.  
  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 Se describe este método.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Cómo: Crear objetos Graphics para dibujar](../advanced/how-to-create-graphics-objects-for-drawing.md)  
 Presenta [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] funcionalidad de gráficos desde una vínculos de perspectiva y proporciona Visual Studio para obtener más información.  
  
 [Variedades de controles personalizados](varieties-of-custom-controls.md)  
 Describe los tipos de controles personalizados que puede crear.
