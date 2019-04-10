---
title: Procedimientos recomendados para el control TableLayoutPanel
ms.date: 03/30/2017
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
ms.openlocfilehash: 57abf3527af146f1ce918bcabbc6a5a34bfb9b34
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222333"
---
# <a name="best-practices-for-the-tablelayoutpanel-control"></a>Procedimientos recomendados para el control TableLayoutPanel
El <xref:System.Windows.Forms.TableLayoutPanel> control proporciona eficaces características de diseño que se deben considerar cuidadosamente antes de usar en los formularios de Windows.  
  
## <a name="recommendations"></a>Recomendaciones  
 Las recomendaciones siguientes le ayudarán a usar el <xref:System.Windows.Forms.TableLayoutPanel> control sacar el máximo partido.  
  
### <a name="targeted-use"></a>Uso de destino  
 Use el <xref:System.Windows.Forms.TableLayoutPanel> controlar con moderación. No se debe usar en todas las situaciones que requieren un diseño de tamaño ajustable. La siguiente lista describe los diseños que se beneficiarían del uso de la <xref:System.Windows.Forms.TableLayoutPanel> control:  
  
-   Diseños en el que hay varias partes del formulario que cambian de tamaño proporcional entre sí.  
  
-   Los diseños que se modificarán o generados dinámicamente en tiempo de ejecución, como formularios de entrada de datos que tienen campos personalizables por el usuario se suma o resta según las preferencias.  
  
-   Diseños que deben permanecer en un tamaño fijo general. Por ejemplo, puede tener un cuadro de diálogo debería ser menor que 800 x 600, pero tiene que admitir las cadenas localizadas.  
  
 La siguiente lista describe los diseños que no se benefician enormemente de utilizando el <xref:System.Windows.Forms.TableLayoutPanel> control:  
  
-   Formularios de entrada de datos simple con una sola columna de etiquetas y una sola columna de áreas de entrada de texto.  
  
-   Área que debería rellenar todo el espacio disponible cuando se produce un cambio de tamaño de presentación de formularios con una sola grande. Un ejemplo de esto es un formulario que muestra una sola <xref:System.Windows.Forms.PropertyGrid> control. En este caso, utilice el anclaje, porque nada debe expandir al tamaño del formulario.  
  
 Elija cuidadosamente qué controles deben estar en un <xref:System.Windows.Forms.TableLayoutPanel> control. Si tiene espacio para el texto para crecer en un 30% con delimitación, considere el uso de la <xref:System.Windows.Forms.Control.Anchor%2A> solo para la propiedad. Si se puede calcular el espacio requerido por su diseño, el uso de <xref:System.Windows.Forms.Control.Dock%2A> y <xref:System.Windows.Forms.Control.Anchor%2A> es más fácil que calcular los detalles de espacio restante y <xref:System.Windows.Forms.Control.AutoSize%2A> comportamiento.  
  
 En general, al diseñar el diseño con el <xref:System.Windows.Forms.TableLayoutPanel> controlar, mantenga el diseño más simple posible.  
  
### <a name="use-the-document-outline-window"></a>Utilice la ventana Esquema del documento  
 La ventana Esquema del documento proporciona una vista de árbol de su diseño, lo que puede usar para manipular las relaciones de elementos primarios y secundarios y de orden z de los controles. Desde el **menú Ver**, seleccione **Other Windows**, a continuación, seleccione **esquema del documento**.  
  
### <a name="avoid-nesting"></a>Evite el anidamiento  
 Evite el anidamiento otro <xref:System.Windows.Forms.TableLayoutPanel> controla dentro de un <xref:System.Windows.Forms.TableLayoutPanel> control. Puede ser difícil de depurar los diseños anidados.  
  
### <a name="avoid-visual-inheritance"></a>Evite una herencia Visual  
 El <xref:System.Windows.Forms.TableLayoutPanel> control no admite la herencia visual en el Diseñador de Windows Forms. Un <xref:System.Windows.Forms.TableLayoutPanel> aparezca el control en una clase derivada está "bloqueada" en tiempo de diseño.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.TableLayoutPanel>
- <xref:System.Windows.Forms.FlowLayoutPanel>
