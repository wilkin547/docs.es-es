---
title: Procedimientos recomendados para el control TableLayoutPanel
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- layout [Windows Forms]
- TableLayoutPanel control [Windows Forms], best practices
- forms [Windows Forms], best practices
- AutoSize property [Windows Forms], tableLayoutPanel control
- controls [Windows Forms], sizing
- TableLayoutPanel control [Windows Forms], AutoSize behavior
- layout [Windows Forms], AutoSize
- layout [Windows Forms], best practices
- best practices [Windows Forms], tableLayoutPanel control
- sizing [Windows Forms], automatic
- automatic sizing
ms.assetid: b6706efb-d7a4-45ec-8cf4-08fa993e3afb
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 802cc501b695f6c5cfe990bf72a4d9d2af68ba2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Procedimientos recomendados para el control TableLayoutPanel
El <xref:System.Windows.Forms.TableLayoutPanel> control proporciona eficaces características de diseño que se deben considerar cuidadosamente antes de usar en los formularios Windows Forms.  
  
## <a name="recommendations"></a>Recomendaciones  
 Las siguientes recomendaciones le ayudarán a usar el <xref:System.Windows.Forms.TableLayoutPanel> control su para aprovechar al máximo.  
  
### <a name="targeted-use"></a>Uso de destino  
 Use la <xref:System.Windows.Forms.TableLayoutPanel> controlar con moderación. No se debe usar en todas las situaciones que requieren un diseño de tamaño variable. En la lista siguiente describe los diseños que se beneficiarían del uso de la <xref:System.Windows.Forms.TableLayoutPanel> control:  
  
-   Diseños en los que tienen varias partes del formulario que cambian el tamaño proporcionalmente entre sí.  
  
-   Diseños que se pueden modificar ni se generó dinámicamente en tiempo de ejecución, como formularios de entrada de datos que tienen campos personalizables por el usuario agrega o resta según las preferencias.  
  
-   Diseños que deberían permanecer en un tamaño fijo general. Por ejemplo, puede tener un cuadro de diálogo que debería ser menor que 800 x 600, pero debe admitir las cadenas localizadas.  
  
 En la lista siguiente se describe diseños que no se benefician en gran medida del uso de la <xref:System.Windows.Forms.TableLayoutPanel> control:  
  
-   Formularios de entrada de datos simple con una única columna de etiquetas y una única columna de áreas de entrada de texto.  
  
-   Área que debería rellenar todo el espacio disponible cuando se produce un cambio de tamaño de presentación de formularios con una sola grande. Un ejemplo de esto es un formulario que muestra una sola <xref:System.Windows.Forms.PropertyGrid> control. En este caso, utilice el anclaje, porque debería ampliar nada más cuando se cambia el tamaño del formulario.  
  
 Elija cuidadosamente qué controles deben estar en un <xref:System.Windows.Forms.TableLayoutPanel> control. Si dispone de espacio para el texto que se va a crecer en 30% con delimitación, considere el uso de la <xref:System.Windows.Forms.Control.Anchor%2A> solo para la propiedad. Si puede calcular el espacio requerido por su diseño, el uso de <xref:System.Windows.Forms.Control.Dock%2A> y <xref:System.Windows.Forms.Control.Anchor%2A> es más fácil que calcular los detalles de espacio restante y <xref:System.Windows.Forms.Control.AutoSize%2A> comportamiento.  
  
 En general, cuando use un diseño con el <xref:System.Windows.Forms.TableLayoutPanel> controlar, mantenga el diseño más sencilla posible.  
  
### <a name="use-the-document-outline-window"></a>Utilice la ventana Esquema del documento  
 La ventana Esquema del documento proporciona una vista de árbol de la distribución, que puede usar para manipular las relaciones de elementos primarios y secundarios y de orden z de los controles. Desde el **menú Ver**, seleccione **otras ventanas**, a continuación, seleccione **esquema del documento**.  
  
### <a name="avoid-nesting"></a>Evite el anidamiento  
 Evite el anidamiento otro <xref:System.Windows.Forms.TableLayoutPanel> controla dentro de un <xref:System.Windows.Forms.TableLayoutPanel> control. Depurar los diseños anidados puede resultar difícil.  
  
### <a name="avoid-visual-inheritance"></a>Evite una herencia Visual  
 El <xref:System.Windows.Forms.TableLayoutPanel> control no admite la herencia visual en el Diseñador de Windows Forms. Un <xref:System.Windows.Forms.TableLayoutPanel> "bloqueada" en tiempo de diseño que aparezca el control en una clase derivada.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Forms.TableLayoutPanel>  
 <xref:System.Windows.Forms.FlowLayoutPanel>
