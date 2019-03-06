---
title: Procedimiento Utilizar SystemParameters
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- classes [WPF], SystemParameters
ms.assetid: 02e7a5de-94eb-4953-b91c-52e6c872ad5b
ms.openlocfilehash: a05e2d08c989da70dd7763ad2df238aac03fded4
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375160"
---
# <a name="how-to-use-systemparameters"></a>Filtrar Utilizar SystemParameters
En este ejemplo se muestra cómo obtener acceso y usar las propiedades de <xref:System.Windows.SystemParameters> con el fin de estilo de un botón o personalizarlo.  
  
## <a name="example"></a>Ejemplo  
 Los recursos del sistema exponen varias configuraciones basadas en el sistema como recursos para ayudarle a crear objetos visuales coherentes con la configuración del sistema. <xref:System.Windows.SystemParameters> es una clase que contiene las propiedades de valor de parámetro del sistema y las claves de recurso que se enlazan a los valores. Por ejemplo, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> es un <xref:System.Windows.SystemParameters> valor de propiedad y <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A> es la clave de recurso correspondiente.  
  
 En [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)], puede utilizar los miembros de <xref:System.Windows.SystemParameters> como el uso de una propiedad estática o una referencias de recursos dinámicos (con el valor de propiedad estática como clave). Use una referencia de recursos dinámicos si quiere que el valor basado en el sistema se actualice automáticamente mientras se ejecuta la aplicación. De lo contrario, use un recurso estático. Las claves de recurso tienen el sufijo `Key` anexado al nombre de propiedad.  
  
 El ejemplo siguiente muestra cómo obtener acceso y usar los valores estáticos de <xref:System.Windows.SystemParameters> al estilo un botón o personalizarlo. Este ejemplo de marcación se cambia el tamaño de un botón aplicando <xref:System.Windows.SystemParameters> valores a un botón.  
  
 [!code-xaml[SystemRes_snip#ParameterStaticResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml#parameterstaticresources)]  
  
 Para usar los valores de <xref:System.Windows.SystemParameters> en código, no es necesario utilizar referencias estáticas o referencias de recursos dinámicos. En su lugar, use los valores de la <xref:System.Windows.SystemParameters> clase. Aunque las propiedades que no son de clave aparentemente se definen como propiedades estáticas, el comportamiento en tiempo de ejecución de [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] cuando está hospedado en el sistema se vuelva a evaluar las propiedades en tiempo real y representará correctamente los cambios controlado por el usuario a los valores del sistema. El ejemplo siguiente muestra cómo establecer el ancho y alto de un botón mediante el uso de <xref:System.Windows.SystemParameters> valores.  
  
 [!code-csharp[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/Pane1.xaml.cs#parameterresourcescode)]
 [!code-vb[SystemRes_snip#ParameterResourcesCode](~/samples/snippets/visualbasic/VS_Snippets_Wpf/SystemRes_snip/VisualBasic/Pane1.xaml.vb#parameterresourcescode)]  
  
## <a name="see-also"></a>Vea también
- <xref:System.Windows.SystemParameters>
- [Pintar un área con un pincel del sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Usar SystemFonts](how-to-use-systemfonts.md)
- [Usar claves de parámetros del sistema](how-to-use-system-parameters-keys.md)
- [Temas "Cómo..."](resources-how-to-topics.md)
