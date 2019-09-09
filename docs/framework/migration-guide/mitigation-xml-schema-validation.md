---
title: 'Mitigación: validación de esquemas XML'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7f53a2e8684029c0d1329d29a88bd1788e62d43
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70789682"
---
# <a name="mitigation-xml-schema-validation"></a>Mitigación: validación de esquemas XML
En .NET Framework 4.6, la validación de esquemas XSD detecta una infracción de la restricción única si se usa una clave compuesta y una clave está vacía.  
  
## <a name="impact"></a>Impacto  
 El impacto de este cambio debe ser mínimo: según la especificación del esquema, se espera un error de validación de esquema si se infringe `xsd:unique` usando una clave compuesta con una clave vacía.  
  
## <a name="mitigation"></a>Mitigación  
 El hecho de que se detecte un error de validación de esquema si una clave compuesta tiene una clave vacía es una característica configurable:  
  
- A partir de las aplicaciones que tienen como destino .NET Framework 4.6, la detección del error de validación de esquema está habilitada de forma predeterminada, aunque se puede optar por no incluirlo, de manera que no se detecte el error.  
  
- En las aplicaciones que se ejecutan en .NET Framework 4.6, pero que tienen como destino .NET Framework 4.5.2 y versiones anteriores, no se detecta ningún error de validación de esquema de forma predeterminada, aunque se puede optar por recibirlo, de manera que se detecte el error.  
  
 Este comportamiento se puede configurar mediante la clase <xref:System.AppContext> para definir el valor del conmutador `System.Xml.IgnoreEmptyKeySequences`. Dado que el valor predeterminado del modificador es `false` (no se omiten las secuencias de claves vacías), las aplicaciones que tienen como destino .NET Framework 4.6 pueden optar por no recibir el comportamiento usando el siguiente código para establecer el valor del modificador en `true`:  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 Para las aplicaciones destinadas a .NET Framework 4.5.2 y a versiones anteriores, dado que el valor predeterminado del modificador es `true` (se omiten las secuencias de claves vacías), se puede garantizar que una clave compuesta con una clave vacía genera un error de validación de esquema mediante el siguiente código para establecer el valor del modificador en `false`.  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Cambios de redestinación](retargeting-changes-in-the-net-framework-4-6.md)
