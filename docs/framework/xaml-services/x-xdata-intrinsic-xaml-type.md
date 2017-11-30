---
title: "x:XData (Tipo XAML intrínseco)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
caps.latest.revision: "17"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: 3e448c28be6515748254e267b70f3c898b9226a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData (Tipo XAML intrínseco)
Permite la colocación de XML, Islas de datos dentro de una producción de XAML. Elementos XML dentro de `x:XData` no deben tratarse por los procesadores XAML como si fueran una parte del espacio de nombres XAML de manera predeterminada de actuar o cualquier otro espacio de nombres XAML. `x:XData`puede contener código XML arbitrario con formato correcto.  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`elementDataRoot`|El elemento raíz único de la isla de datos adjunta. Para la mayoría de los consumidores eventuales, XML que no tiene una raíz se considera no válida. En concreto, una única raíz es necesaria si la `x:XData` está pensado como un origen de datos XML para WPF o muchas otras tecnologías que usan orígenes de XML para el enlace de datos.|  
|`[elementData]`|Opcional. Código XML que representa los datos XML. Puede contener cualquier número de elementos como los datos del elemento y los elementos anidados pueden estar contenidos en otros elementos; Sin embargo, se aplican las reglas generales de XML.|  
  
## <a name="remarks"></a>Comentarios  
 Los elementos XML dentro de un `x:XData` objeto puede volver a declarar todos los posibles espacios de nombres y prefijos del contenedor XMLDOM dentro de los datos.  
  
 Acceso mediante programación a los datos XML y la `x:XData` tipo XAML intrínseco es posible en los servicios XAML de .NET Framework a través de la <xref:System.Windows.Markup.XData> clase.  
  
## <a name="wpf-usage-notes"></a>Notas de uso WPF  
 El `x:XData` objeto se usa principalmente como un objeto secundario de un <xref:System.Windows.Data.XmlDataProvider>, o bien, como el objeto secundario de la <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> propiedad (en XAML, esto se expresa normalmente en la sintaxis de elemento de propiedad).  
  
 Los datos normalmente deben volver a definir el espacio de nombres XML base dentro de la isla de datos como un nuevo espacio de nombres XML (establecido en una cadena vacía). Esto es más fácil para islas de datos simple porque la <xref:System.Windows.Data.Binding.XPath%2A> expresiones que se usan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos. Islas de datos más complejas pueden definir varios prefijos para los datos y usar un prefijo concreto para el espacio de nombres XML en la raíz. En este caso, todas las <xref:System.Windows.Data.Binding.XPath%2A> las referencias a expresiones deben incluir el prefijo de espacio de nombres asignado adecuado. Para obtener más información, consulte [Información general sobre el enlace de datos](../../../docs/framework/wpf/data/data-binding-overview.md).  
  
 Técnicamente, `x:XData` puede utilizarse como el contenido de cualquier propiedad de tipo <xref:System.Xml.Serialization.IXmlSerializable>. Sin embargo, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> es la única implementación notable.  
  
## <a name="see-also"></a>Vea también  
 <xref:System.Windows.Data.XmlDataProvider>  
 [Información general sobre el enlace de datos](../../../docs/framework/wpf/data/data-binding-overview.md)  
 [Binding (extensión de marcado)](../../../docs/framework/wpf/advanced/binding-markup-extension.md)
