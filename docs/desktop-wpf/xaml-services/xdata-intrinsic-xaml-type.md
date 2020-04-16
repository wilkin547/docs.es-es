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
ms.openlocfilehash: b7f0954158988db107feb4a6c51ba81d5db11dcb
ms.sourcegitcommit: c2d9718996402993cf31541f11e95531bc68bad0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/27/2020
ms.locfileid: "81432795"
---
# <a name="xxdata-intrinsic-xaml-type"></a>x:XData (Tipo XAML intrínseco)
Habilita la colocación de islas de datos XML dentro de una producción XAML. Los procesadores XAML no `x:XData` deben tratar los elementos XML dentro como si formaran parte del espacio de nombres XAML predeterminado que actúa o de cualquier otro espacio de nombres XAML. `x:XData`puede contener XML arbitrario bien formado.

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
|`elementDataRoot`|El único elemento raíz de la isla de datos cerrada. Para la mayoría de los consumidores eventuales, XML que no tiene una sola raíz se considera no válido. En concreto, se requiere una `x:XData` única raíz si está pensado como un origen de datos XML para WPFo o muchas otras tecnologías que usan orígenes XML para el enlace de datos.|
|`[elementData]`|Opcional. XML que representa los datos XML. Cualquier número de elementos puede contenerse como datos de elemento y los elementos anidados pueden estar contenidos en otros elementos; sin embargo, se aplican las reglas generales de XML.|

## <a name="remarks"></a>Observaciones

Los elementos `x:XData` XML dentro de un objeto pueden volver a declarar todos los espacios de nombres y prefijos posibles del XMLDOM contenedor dentro de los datos.

El acceso mediante programación `x:XData` a los datos XML y el <xref:System.Windows.Markup.XData> tipo XAML intrínseco es posible en los servicios XAML de .NET a través de la clase.

## <a name="wpf-usage-notes"></a>Notas de uso de WPF

El `x:XData` objeto se utiliza principalmente como <xref:System.Windows.Data.XmlDataProvider>un objeto secundario de un <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> , o alternativamente, como el objeto secundario de la propiedad (en XAML, esto se expresa normalmente en la sintaxis del elemento de propiedad).

Normalmente, los datos deben redefinir el espacio de nombres XML base dentro de la isla de datos para que sea un nuevo espacio de nombres XML predeterminado (establecido en una cadena vacía). Esto es más fácil para <xref:System.Windows.Data.Binding.XPath%2A> las islas de datos simples porque las expresiones que se utilizan para hacer referencia y enlazar a los datos pueden evitar la inclusión de prefijos. Las islas de datos más complejas podrían definir varios prefijos para los datos y usar un prefijo específico para el espacio de nombres XML en la raíz. En este caso, todas las <xref:System.Windows.Data.Binding.XPath%2A> referencias de expresión deben incluir el prefijo asignado al espacio de nombres adecuado. Para obtener más información, vea [Información general sobre el enlace](../data/data-binding-overview.md)de datos .

Técnicamente, `x:XData` se puede utilizar como el <xref:System.Xml.Serialization.IXmlSerializable>contenido de cualquier propiedad de tipo . Sin <xref:System.Windows.Data.XmlDataProvider.XmlSerializer%2A?displayProperty=nameWithType> embargo, es la única implementación prominente.

## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Data.XmlDataProvider>
- [Descripción general del enlace de datos](../data/data-binding-overview.md)
- [Enlazar extensión de marcado](../../framework/wpf/advanced/binding-markup-extension.md)
