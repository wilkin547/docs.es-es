---
title: 'Cómo: Utilizar SystemParameters'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: 07b73d78a022e508f9ed8ca2e80b71bc2ab89910
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-use-systemparameters"></a>Cómo: Utilizar SystemParameters
Este ejemplo muestra cómo obtener acceso y utilizar las propiedades de <xref:System.Windows.SystemParameters> para aplicar estilo a un botón o personalizarlo.  
  
## <a name="example"></a>Ejemplo  
 Los recursos del sistema exponen varias configuraciones basadas en el sistema como recursos para ayudarle a crear objetos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemParameters> es una clase que contiene propiedades de valor del parámetro de sistema y las claves de recursos que se enlazan a los valores. Por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> es un <xref:System.Windows.SystemParameters> valor de propiedad y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> es la clave de recurso correspondiente.  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede utilizar los miembros de <xref:System.Windows.SystemParameters> como el uso de una propiedad estática o referencias de recurso dinámicas (con el valor de propiedad estática como la clave). Use una referencia de recursos dinámicos si quiere que el valor basado en el sistema se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático. Las claves de recurso tienen el sufijo `Key` anexado al nombre de propiedad.  
  
 En el ejemplo siguiente se muestra cómo obtener acceso y utilizar los valores estáticos de <xref:System.Windows.SystemParameters> para aplicar estilo a un botón o personalizarlo. Este ejemplo de marcado se cambia el tamaño de un botón mediante la aplicación <xref:System.Windows.SystemParameters> valores a un botón.  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Para usar los valores de <xref:System.Windows.SystemParameters> en el código, no es necesario utilizar referencias estáticas o referencias de recursos dinámicos. En su lugar, use los valores de la <xref:System.Windows.SystemParameters> clase. Aunque las propiedades de clave no aparentemente se definen como propiedades estáticas, el comportamiento en tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando está hospedado en el sistema se vuelve a evaluar las propiedades en tiempo real, y de correctamente explicar los cambios controlados por el usuario a valores del sistema. En el ejemplo siguiente se muestra cómo establecer el ancho y alto de un botón mediante el uso de <xref:System.Windows.SystemParameters> valores.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.SystemParameters>  
 [Pintar un área con un pincel del sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Usar SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [Usar claves de parámetros del sistema](../../../../docs/framework/wpf/advanced/how-to-use-system-parameters-keys.md)  
 [Temas "Cómo..."](../../../../docs/framework/wpf/advanced/resources-how-to-topics.md)
