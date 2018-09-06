---
title: Serialización selectiva
ms.date: 08/07/2017
dev_langs:
- CSharp
helpviewer_keywords:
- serialization, selective serialization
- binary serialization, selective serialization
ms.assetid: 39c56635-95d2-4afd-aff1-b022e7649bb3
ms.openlocfilehash: 74e21045ec70faf6ee82200a15362d51edf61433
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43879290"
---
# <a name="selective-serialization"></a>Serialización selectiva
Una clase a menudo contiene campos que no se deberían serializar. Por ejemplo, suponga que una clase almacena un Identificador de subproceso en una variable miembro. Al deserializar la clase, es posible que el subproceso que ha almacenado el identificador al serializar la clase ya no se esté ejecutando; así, serializar este valor no tiene sentido. Puede evitar que las variables miembro se serialicen si las marca con el atributo [NonSerialized](xref:System.NonSerializedAttribute) como se indica a continuación.  
  
```csharp  
[Serializable]  
public class MyObject   
{  
  public int n1;  
  [NonSerialized] public int n2;  
  public String str;  
}  
```

Si es posible, haz que un objeto pueda contener datos seguros no serializables. Si se debe serializar el objeto, aplique el atributo `NonSerialized` a campos concretos que almacenen datos confidenciales. Si no excluye estos campos de la serialización, sea consciente de que los datos que almacenan se exponen a cualquier código que tenga permiso para serializar. Para más información sobre cómo escribir código de serialización seguro, vea [Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md).

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a>Vea también

- [Serialización binaria](binary-serialization.md)  
- [Serialización SOAP y XML](xml-and-soap-serialization.md)  
- [Seguridad y serialización](../../../docs/framework/misc/security-and-serialization.md)
