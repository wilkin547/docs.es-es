---
title: 'Mitigación: validación de esquemas XML'
description: La validación de esquemas XSD detecta una infracción de la restricción única si se usa una clave compuesta y una clave está vacía en .NET Framework 4.6.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
ms.openlocfilehash: 0672361ca5c0bc7cb6ec166f59278b93555e0947
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475312"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="9ff36-103">Mitigación: validación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="9ff36-103">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="9ff36-104">En .NET Framework 4.6, la validación de esquemas XSD detecta una infracción de la restricción única si se usa una clave compuesta y una clave está vacía.</span><span class="sxs-lookup"><span data-stu-id="9ff36-104">In the .NET Framework 4.6, XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="9ff36-105">Impacto</span><span class="sxs-lookup"><span data-stu-id="9ff36-105">Impact</span></span>  
 <span data-ttu-id="9ff36-106">El impacto de este cambio debe ser mínimo: según la especificación del esquema, se espera un error de validación de esquema si se infringe `xsd:unique` usando una clave compuesta con una clave vacía.</span><span class="sxs-lookup"><span data-stu-id="9ff36-106">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="9ff36-107">Mitigación</span><span class="sxs-lookup"><span data-stu-id="9ff36-107">Mitigation</span></span>  
 <span data-ttu-id="9ff36-108">El hecho de que se detecte un error de validación de esquema si una clave compuesta tiene una clave vacía es una característica configurable:</span><span class="sxs-lookup"><span data-stu-id="9ff36-108">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
- <span data-ttu-id="9ff36-109">A partir de las aplicaciones que tienen como destino .NET Framework 4.6, la detección del error de validación de esquema está habilitada de forma predeterminada, aunque se puede optar por no incluirlo, de manera que no se detecte el error.</span><span class="sxs-lookup"><span data-stu-id="9ff36-109">Starting with the apps that target the .NET Framework 4.6, detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
- <span data-ttu-id="9ff36-110">En las aplicaciones que se ejecutan en .NET Framework 4.6, pero que tienen como destino .NET Framework 4.5.2 y versiones anteriores, no se detecta ningún error de validación de esquema de forma predeterminada, aunque se puede optar por recibirlo, de manera que se detecte el error.</span><span class="sxs-lookup"><span data-stu-id="9ff36-110">In apps that run under the .NET Framework 4.6 but target the .NET Framework 4.5.2 and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="9ff36-111">Este comportamiento se puede configurar mediante la clase <xref:System.AppContext> para definir el valor del conmutador `System.Xml.IgnoreEmptyKeySequences`.</span><span class="sxs-lookup"><span data-stu-id="9ff36-111">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="9ff36-112">Dado que el valor predeterminado del modificador es `false` (no se omiten las secuencias de claves vacías), las aplicaciones que tienen como destino .NET Framework 4.6 pueden optar por no recibir el comportamiento usando el siguiente código para establecer el valor del modificador en `true`:</span><span class="sxs-lookup"><span data-stu-id="9ff36-112">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the .NET Framework 4.6 can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="9ff36-113">Para las aplicaciones destinadas a .NET Framework 4.5.2 y a versiones anteriores, dado que el valor predeterminado del modificador es `true` (se omiten las secuencias de claves vacías), se puede garantizar que una clave compuesta con una clave vacía genera un error de validación de esquema mediante el siguiente código para establecer el valor del modificador en `false`.</span><span class="sxs-lookup"><span data-stu-id="9ff36-113">For apps that target the .NET Framework 4.5.2 and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9ff36-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ff36-114">See also</span></span>

- [<span data-ttu-id="9ff36-115">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="9ff36-115">Application compatibility</span></span>](application-compatibility.md)
