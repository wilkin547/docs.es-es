---
title: Xml (propiedad dinámica de XElement)
ms.date: 10/22/2019
ms.topic: reference
apiname:
- XElement.Xml
ms.openlocfilehash: 9bac9797f397a0bea1dda36bf864f88293061893
ms.sourcegitcommit: 82f94a44ad5c64a399df2a03fa842db308185a76
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/25/2019
ms.locfileid: "72921039"
---
# <a name="xml-xelement-dynamic-property"></a>Xml (propiedad dinámica de XElement)

Obtiene el contenido XML sin formato del elemento.

## <a name="syntax"></a>Sintaxis

```xaml
elem.Xml
```

## <a name="property-valuereturn-value"></a>Valor de propiedad y valor devuelto

Un <xref:System.String> que representa el contenido XML sin formato del elemento.

## <a name="remarks"></a>Comentarios

Esta propiedad es equivalente al método <xref:System.Xml.Linq.XNode.ToString(System.Xml.Linq.SaveOptions)> de la clase <xref:System.Xml.Linq.XNode?displayProperty=fullName>, con el parámetro `SaveOptions` establecido en <xref:System.Xml.Linq.SaveOptions>.

## <a name="see-also"></a>Vea también

- [Propiedades dinámicas de la clase XElement](attribute-xelement-dynamic-property.md)
- [Valor](value-xelement-dynamic-property.md)
