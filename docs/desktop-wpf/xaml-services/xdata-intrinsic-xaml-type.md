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
ms.openlocfilehash: d78c2fd63192dc499b119e5b038b92555511a695
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544809"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData (Tipo XAML intrínseco)
Habilita la colocación de las islas de datos XML dentro de un entorno de producción XAML. Los elementos XML de `x:XData` no deben ser tratados por los procesadores XAML como si formaran parte del espacio de nombres XAML predeterminado que actúa o cualquier otro espacio de nombres XAML. `x:XData` puede contener XML con formato correcto arbitrario.

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
|`elementDataRoot`|Elemento raíz único de la isla de datos delimitada. Para la mayoría de los consumidores eventuales, XML que no tiene una sola raíz se considera no válido. En concreto, se requiere una sola raíz si `x:XData` se ha diseñado como origen de datos XML para WPF o muchas otras tecnologías que usan orígenes XML para el enlace de datos.|
|`[elementData]`|Opcional. XML que representa los datos XML. Se puede incluir cualquier número de elementos como datos de elemento y los elementos anidados pueden estar contenidos en otros elementos; sin embargo, se aplican las reglas generales de XML.|

## <a name="remarks"></a>Comentarios

Los elementos XML dentro de un `x:XData` objeto pueden volver a declarar todos los espacios de nombres y prefijos posibles del que contiene XMLDOM dentro de los datos.

El acceso mediante programación a los datos XML y el `x:XData` tipo XAML intrínseco es posible en los servicios XAML de .net a través de la <xref:System.Windows.Markup.XData> clase.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

El `x:XData` objeto se utiliza principalmente como un objeto secundario de <xref:System.Windows.Data.XmlDataProvider> , o como alternativa, como el objeto secundario de la <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> propiedad (en XAML, normalmente se expresa en la sintaxis de elementos de propiedad).

Normalmente, los datos deben volver a definir el espacio de nombres XML base dentro de la isla de datos para que sea un nuevo espacio de nombres XML predeterminado (establecido en una cadena vacía). Esto es más fácil para las islas de datos simples porque las <xref:System.Windows.Data.Binding.XPath%2A> expresiones que se usan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos. Las islas de datos más complejas pueden definir varios prefijos para los datos y usar un prefijo específico para el espacio de nombres XML en la raíz. En este caso, todas <xref:System.Windows.Data.Binding.XPath%2A> las referencias a expresiones deben incluir el prefijo asignado por espacio de nombres adecuado. Para obtener más información, vea [información general sobre el enlace de datos](../data/data-binding-overview.md).

Técnicamente, `x:XData` se puede utilizar como contenido de cualquier propiedad de tipo <xref:System.Xml.Serialization.IXmlSerializable> . Sin embargo, <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> es la única implementación destacada.

## <a name="see-also"></a>Vea también

- <xref:System.Windows.Data.XmlDataProvider>
- [Información general sobre el enlace de datos](../data/data-binding-overview.md)
- [Binding (extensión de marcado)](/dotnet/desktop/wpf/advanced/binding-markup-extension)
