---
author: dotpaul
ms.author: paulming
ms.date: 05/01/2019
ms.topic: include
ms.openlocfilehash: cf944ae9ca200d34a1f0f32e68bf3aee73a9500a
ms.sourcegitcommit: c04535ad05e374fb269fcfc6509217755fbc0d54
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2020
ms.locfileid: "96592139"
---
- Si es posible, use un serializador seguro en su lugar y **no permita que un atacante especifique un tipo arbitrario para deserializar**. Algunos serializadores más seguros incluyen:

  - <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=nameWithType>
  - <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer?displayProperty=nameWithType>
  - <xref:System.Web.Script.Serialization.JavaScriptSerializer?displayProperty=nameWithType> : No usar nunca <xref:System.Web.Script.Serialization.SimpleTypeResolver?displayProperty=nameWithType> . Si debe usar un solucionador de tipos, restrinja los tipos deserializados a una lista de espera.
  - <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>
  - Newtonsoft Json.NET: Use TypeNameHandling. None. Si debe usar otro valor para TypeNameHandling, restrinja los tipos deserializados a una lista de espera con un ISerializationBinder personalizado.
  - Búferes de protocolo

- Convierta la prueba de alteración de los datos serializados. Después de la serialización, firme criptográficamente los datos serializados. Antes de la deserialización, valide la firma criptográfica. Proteja la clave criptográfica para que no se revele y diseñe las rotaciones de clave.
