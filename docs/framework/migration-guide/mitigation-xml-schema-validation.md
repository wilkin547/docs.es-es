---
title: 'Mitigación: validación de esquemas XML'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e757962f02cce104d8c5ab805d0481861cab426e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33389218"
---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="0a595-102">Mitigación: validación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="0a595-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="0a595-103">En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la validación de esquemas XSD detecta una infracción de la restricción única si se usa una clave compuesta y una clave está vacía.</span><span class="sxs-lookup"><span data-stu-id="0a595-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="0a595-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="0a595-104">Impact</span></span>  
 <span data-ttu-id="0a595-105">El impacto de este cambio debe ser mínimo: según la especificación del esquema, se espera un error de validación de esquema si se infringe `xsd:unique` usando una clave compuesta con una clave vacía.</span><span class="sxs-lookup"><span data-stu-id="0a595-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="0a595-106">Mitigación</span><span class="sxs-lookup"><span data-stu-id="0a595-106">Mitigation</span></span>  
 <span data-ttu-id="0a595-107">El hecho de que se detecte un error de validación de esquema si una clave compuesta tiene una clave vacía es una característica configurable:</span><span class="sxs-lookup"><span data-stu-id="0a595-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="0a595-108">a partir de las aplicaciones que tiene como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la detección del error de validación de esquema está habilitada de forma predeterminada, aunque se puede optar por no incluirlo, de manera que no se detecte el error.</span><span class="sxs-lookup"><span data-stu-id="0a595-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="0a595-109">En las aplicaciones que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] pero que tienen como destino [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] y versiones anteriores, no se detecta ningún error de validación de esquema de forma predeterminada, aunque se puede optar por incluirlo, de manera que se detecte el error.</span><span class="sxs-lookup"><span data-stu-id="0a595-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="0a595-110">Este comportamiento se puede configurar mediante la clase <xref:System.AppContext> para definir el valor del conmutador `System.Xml.IgnoreEmptyKeySequences`.</span><span class="sxs-lookup"><span data-stu-id="0a595-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="0a595-111">Dado que el valor predeterminado del modificador  es `false` (no se omiten las secuencias de claves vacías), las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] pueden optar por no incluir el comportamiento usando el siguiente código para establecer el valor del modificador en `true`:</span><span class="sxs-lookup"><span data-stu-id="0a595-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]  
  
 <span data-ttu-id="0a595-112">Para las aplicaciones destinadas a [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] y a versiones anteriores, dado que el valor predeterminado del modificador es `true` (se omiten las secuencias de claves vacías), se puede garantizar que una clave compuesta con una clave vacía genera un error de validación de esquema mediante el siguiente código para establecer el valor del modificador en `false`.</span><span class="sxs-lookup"><span data-stu-id="0a595-112">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 [!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)]
 [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0a595-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a595-113">See Also</span></span>  
 [<span data-ttu-id="0a595-114">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="0a595-114">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)
