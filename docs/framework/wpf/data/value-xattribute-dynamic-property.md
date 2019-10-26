---
title: Value (propiedad dinámica de XAttribute)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XAttribute.Value
apitype: Assembly
ms.openlocfilehash: 32c15a89a976b5f9af12f040c43e724a25357ead
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72920979"
---
# <a name="value-xattribute-dynamic-property"></a>Value (propiedad dinámica de XAttribute)

Obtiene o establece el valor del atributo XML.

## <a name="syntax"></a>Sintaxis

```xaml
attrib.Value
```

## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto

<xref:System.String> que contiene el valor de este atributo.

## <a name="exceptions"></a>Excepciones

|Tipo de excepción|Condición|
| - |---------------|
|<xref:System.ArgumentNullException>|Cuando se establece, el parámetro `value` es `null`.|

## <a name="remarks"></a>Comentarios

Esta propiedad es equivalente a la propiedad <xref:System.Xml.Linq.XAttribute.Value%2A> de la clase <xref:System.Xml.Linq.XAttribute?displayProperty=fullName>, pero su propiedad dinámica también admite las notificaciones de cambio.

## <a name="see-also"></a>Vea también

- <xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>
- [Propiedades dinámicas de la clase XAttribute](value-xattribute-dynamic-property.md)
- [Attribute](attribute-xelement-dynamic-property.md)
