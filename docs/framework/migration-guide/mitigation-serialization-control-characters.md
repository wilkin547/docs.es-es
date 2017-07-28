---
title: "Mitigación: Serialización del caracteres de control con DataContractJsonSerializer"
ms.custom: 
ms.date: 04/07/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- .NET Framework 4.7 retargeting changes
- retargeting changes
- DataContractJsonSerializer changes
- serialization changes
ms.assetid: e065d458-a128-44f2-9f17-66af9d5be954
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 6da580d208736a64e2094f701fb4c1241a488322
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-serialization-of-control-characters-with-the-datacontractjsonserializer"></a>Mitigación: Serialización del caracteres de control con DataContractJsonSerializer

A partir de NET Framework 4.7, ha cambiado la forma en la que se serializan los caracteres de control con <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> para que sean conformes con ECMAScript V6 y V8. 
 
## <a name="impact"></a>Impacto

En .NET Framework 4.6.2 y versiones anteriores, el elemento <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> no serializaba algunos caracteres de control especiales, como `\b`, `\f` y `\t`, de forma que era compatible con los estándares de ECMAScript V6 y V8.

Para las aplicaciones destinadas a versiones de .NET Framework a partir de .NET Framework 4.7, la serialización de estos caracteres de control es compatible con ECMAScript V6 y V8. Afecta a las siguientes API:

- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A> 
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>
- <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer.WriteObject%2A>

## <a name="mitigation"></a>Mitigación

Para aplicaciones destinadas a versiones de .NET Framework a partir de .NET Framework 4.7, este comportamiento está habilitado de forma predeterminada.

Si no desea este compartimiento, puede rechazar esta característica agregando la siguiente línea a la sección `<runtime>` del archivo app.config o web.config:

```xml
<runtime>
   <AppContextSwitchOverrides value="Switch.System.Runtime.Serialization.DoNotUseECMAScriptV6EscapeControlCharacter=false" />
</runtime>
```
 
## <a name="see-also"></a>Vea también
[Cambios de redestinación en .NET Framework 4.7](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-7.md)

