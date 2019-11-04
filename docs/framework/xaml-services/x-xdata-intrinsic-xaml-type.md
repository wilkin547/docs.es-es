---
title: x:XData (Tipo XAML intrínseco)
ms.date: 03/30/2017
f1_keywords:
- x:XData
- XData
- xXData
helpviewer_keywords:
- XAML [XAML Services], x:XData directive element
- XData in XAML [XAML Services]
- x:XData XAML directive element [XAML Services]
ms.assetid: 7ce209c2-621b-4977-b643-565f7e663534
ms.openlocfilehash: 8496e7c87cf7e6eea996ca7af4f288b7495c7661
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2019
ms.locfileid: "73459903"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData (Tipo XAML intrínseco)
Habilita la colocación de las islas de datos XML dentro de un entorno de producción XAML. Los elementos XML dentro de `x:XData` no deben ser tratados por procesadores XAML como si formaran parte del espacio de nombres XAML predeterminado de la acción o cualquier otro espacio de nombres XAML. `x:XData` puede contener XML con formato correcto arbitrario.  
  
## <a name="xaml-object-element-usage"></a>Uso de elementos de objeto XAML  
  
```xaml  
<x:XData>  
  <elementDataRoot>  
    [elementData]  
  </elementDataRoot>  
</x:XData>  
```  
  
## <a name="xaml-values"></a>Valores XAML  
  
|||  
|-|-|  
|`elementDataRoot`|Elemento raíz único de la isla de datos delimitada. Para la mayoría de los consumidores eventuales, XML que no tiene una sola raíz se considera no válido. En concreto, se requiere una sola raíz si el `x:XData` está pensado como un origen de datos XML para WPF o muchas otras tecnologías que usan orígenes XML para el enlace de datos.|  
|`[elementData]`|Opcional. XML que representa los datos XML. Se puede incluir cualquier número de elementos como datos de elemento y los elementos anidados pueden estar contenidos en otros elementos; sin embargo, se aplican las reglas generales de XML.|  
  
## <a name="remarks"></a>Comentarios  
 Los elementos XML dentro de un objeto `x:XData` pueden volver a declarar todos los espacios de nombres y prefijos posibles del que contiene XMLDOM dentro de los datos.  
  
 El acceso mediante programación a los datos XML y el tipo XAML intrínseco `x:XData` es posible en .NET Framework servicios XAML a través de la clase <xref:System.Windows.Markup.XData>.  
  
## <a name="wpf-usage-notes"></a>Notas de uso de WPF  
 El objeto `x:XData` se utiliza principalmente como un objeto secundario de un <xref:System.Windows.Data.XmlDataProvider>, o como alternativa, como el objeto secundario de la propiedad <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> (en XAML, normalmente se expresa en sintaxis de elementos de propiedad).  
  
 Normalmente, los datos deben volver a definir el espacio de nombres XML base dentro de la isla de datos para que sea un nuevo espacio de nombres XML predeterminado (establecido en una cadena vacía). Esto es más fácil para las islas de datos simples porque las expresiones <xref:System.Windows.Data.Binding.XPath%2A> que se usan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos. Las islas de datos más complejas pueden definir varios prefijos para los datos y usar un prefijo específico para el espacio de nombres XML en la raíz. En este caso, todas las referencias de expresión de <xref:System.Windows.Data.Binding.XPath%2A> deben incluir el prefijo asignado por espacio de nombres adecuado. Para obtener más información, consulte [Información general sobre el enlace de datos](../../desktop-wpf/data/data-binding-overview.md).  
  
 Técnicamente, `x:XData` se puede utilizar como contenido de cualquier propiedad de tipo <xref:System.Xml.Serialization.IXmlSerializable>. Sin embargo, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> es la única implementación destacada.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.XmlDataProvider>
- [Información general sobre el enlace de datos](../../desktop-wpf/data/data-binding-overview.md)
- [Binding (extensión de marcado)](../wpf/advanced/binding-markup-extension.md)
