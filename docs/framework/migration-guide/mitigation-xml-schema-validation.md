---
title: "Mitigación: validación de esquemas XML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b73dd4f4-f2dc-47a2-9425-3896e92321fb
caps.latest.revision: 7
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 786e2d0d70aaead6d464d262ca43dade8db64a52
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-xml-schema-validation"></a><span data-ttu-id="807b1-102">Mitigación: validación de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="807b1-102">Mitigation: XML Schema Validation</span></span>
<span data-ttu-id="807b1-103">En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la validación de esquemas XSD detecta una infracción de la restricción única si se usa una clave compuesta y una clave está vacía.</span><span class="sxs-lookup"><span data-stu-id="807b1-103">In the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], XSD schema validation detects a violation of the unique constraint if a compound key is used and one key is empty.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="807b1-104">Impacto</span><span class="sxs-lookup"><span data-stu-id="807b1-104">Impact</span></span>  
 <span data-ttu-id="807b1-105">El impacto de este cambio debe ser mínimo: según la especificación del esquema, se espera un error de validación de esquema si se infringe `xsd:unique` usando una clave compuesta con una clave vacía.</span><span class="sxs-lookup"><span data-stu-id="807b1-105">The impact of this change should be minimal: based on the schema specification, a schema validation error is expected if `xsd:unique` is violated by using a compound key with an empty key.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="807b1-106">Mitigación</span><span class="sxs-lookup"><span data-stu-id="807b1-106">Mitigation</span></span>  
 <span data-ttu-id="807b1-107">El hecho de que se detecte un error de validación de esquema si una clave compuesta tiene una clave vacía es una característica configurable:</span><span class="sxs-lookup"><span data-stu-id="807b1-107">Whether a schema validation error is detected if a compound key has one empty key is a configurable feature:</span></span>  
  
-   <span data-ttu-id="807b1-108">a partir de las aplicaciones que tiene como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], la detección del error de validación de esquema está habilitada de forma predeterminada, aunque se puede optar por no incluirlo, de manera que no se detecte el error.</span><span class="sxs-lookup"><span data-stu-id="807b1-108">Starting with the apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], detection of the schema validation error is enabled by default; however, it is possible to opt out of it, so that the schema validation error will not be detected.</span></span>  
  
-   <span data-ttu-id="807b1-109">En las aplicaciones que se ejecutan en [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] pero que tienen como destino [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] y versiones anteriores, no se detecta ningún error de validación de esquema de forma predeterminada, aunque se puede optar por incluirlo, de manera que se detecte el error.</span><span class="sxs-lookup"><span data-stu-id="807b1-109">In apps that run under the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] but target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, a schema validation error is not detected by default; however, it is possible to opt into it, so that the schema validation error will be detected.</span></span>  
  
 <span data-ttu-id="807b1-110">Este comportamiento se puede configurar mediante la clase <xref:System.AppContext> para definir el valor del conmutador `System.Xml.IgnoreEmptyKeySequences`.</span><span class="sxs-lookup"><span data-stu-id="807b1-110">This behavior can be configured by using the <xref:System.AppContext> class to define the value of the `System.Xml.IgnoreEmptyKeySequences` switch.</span></span> <span data-ttu-id="807b1-111">Dado que el valor predeterminado del modificador  es `false` (no se omiten las secuencias de claves vacías), las aplicaciones que tienen como destino [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] pueden optar por no incluir el comportamiento usando el siguiente código para establecer el valor del modificador en `true`:</span><span class="sxs-lookup"><span data-stu-id="807b1-111">Because the switch's default value is `false` (empty key sequences are not ignored), apps that target the [!INCLUDE[net_v46](../../../includes/net-v46-md.md)] can opt out of the behavior by using the following code to set the switch's value to `true`:</span></span>  
  
 <span data-ttu-id="807b1-112">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="807b1-112">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#1)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#1)]</span></span>  
  
 <span data-ttu-id="807b1-113">Para las aplicaciones destinadas a [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] y a versiones anteriores, dado que el valor predeterminado del modificador es `true` (se omiten las secuencias de claves vacías), se puede garantizar que una clave compuesta con una clave vacía genera un error de validación de esquema mediante el siguiente código para establecer el valor del modificador en `false`.</span><span class="sxs-lookup"><span data-stu-id="807b1-113">For apps that target the [!INCLUDE[net_v452](../../../includes/net-v452-md.md)] and earlier versions, because the switch's default value is `true` (empty key sequences are ignored), it is possible to ensure that a compound key with an empty key does generate a schema validation error by using the following code to set the switch's value to `false`.</span></span>  
  
 <span data-ttu-id="807b1-114">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="807b1-114">[!code-csharp[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/cs/program.cs#2)] [!code-vb[AppCompat.IgnoreEmptyKeySequences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/appcompat.ignoreemptykeysequences/vb/module1.vb#2)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="807b1-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="807b1-115">See Also</span></span>  
 [<span data-ttu-id="807b1-116">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="807b1-116">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

