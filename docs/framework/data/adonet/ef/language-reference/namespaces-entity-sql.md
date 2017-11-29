---
title: Espacios de nombres (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 0ea5292d20aebdb27da726b0076179fb64631e5c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="9aa4a-102">Espacios de nombres (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="9aa4a-102">Namespaces (Entity SQL)</span></span>
[!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="9aa4a-103"> introduce espacios de nombres para evitar conflictos de nombres en los identificadores globales como los nombres de tipos, los conjuntos de entidades, las funciones, etcétera.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-103"> introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="9aa4a-104">La compatibilidad de espacio de nombres en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es similar a la compatibilidad de espacio de nombres en el [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9aa4a-104">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)].</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="9aa4a-105"> proporciona dos formas de cláusula USING: espacios de nombres completos, a los que se proporciona un alias más breve, y espacios no completos, según se ilustra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9aa4a-105"> provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="9aa4a-106">Reglas de la resolución de nombres</span><span class="sxs-lookup"><span data-stu-id="9aa4a-106">Name Resolution Rules</span></span>  
 <span data-ttu-id="9aa4a-107">Si no se puede resolver un identificador en los ámbitos locales, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta localizar el nombre en los ámbitos globales (los espacios de nombres).</span><span class="sxs-lookup"><span data-stu-id="9aa4a-107">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="9aa4a-108"> primero intenta buscar la coincidencia del identificador (prefijo) con uno de los espacios de nombres completos.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-108"> first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="9aa4a-109">Si se encuentra una coincidencia, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] para intentar resolver el resto del identificador en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-109">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="9aa4a-110">Si no se encuentra ninguna coincidencia, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-110">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="9aa4a-111">Después, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta buscar todos los espacios no completos (especificados en el prólogo) para el identificador.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-111">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="9aa4a-112">Si el identificador se puede encontrar en un espacio de nombres exactamente, se devuelve esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-112">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="9aa4a-113">Si hay una coincidencia con ese identificador en más de un espacio de nombres, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-113">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="9aa4a-114">Si no se puede identificar ningún espacio de nombres para el identificador, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] pasa el nombre al siguiente ámbito exterior (el <xref:System.Data.Common.DbCommand> o <xref:System.Data.Common.DbConnection> objeto), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="9aa4a-114">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="9aa4a-115">Diferencias con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="9aa4a-115">Differences from the .NET Framework</span></span>  
 <span data-ttu-id="9aa4a-116">En [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], puede usar espacios de nombres parciales.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-116">In the [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)], you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)]<span data-ttu-id="9aa4a-117"> no permite esto.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-117"> does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="9aa4a-118">Uso de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="9aa4a-118">ADO.NET Usage</span></span>  
 <span data-ttu-id="9aa4a-119">Las consultas se expresan a través de objetos <xref:System.Data.Common.DbCommand> de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-119">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="9aa4a-120">Los objetos <xref:System.Data.Common.DbCommand> se pueden generar sobre los objetos <xref:System.Data.Common.DbConnection>.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-120"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="9aa4a-121">Los espacios de nombres también se pueden especificar como parte de los objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbConnection>.</span><span class="sxs-lookup"><span data-stu-id="9aa4a-121">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="9aa4a-122">Si [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no se puede resolver un identificador dentro de la propia consulta, los espacios de nombres externos se sondean (en función de reglas similares).</span><span class="sxs-lookup"><span data-stu-id="9aa4a-122">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9aa4a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9aa4a-123">See Also</span></span>  
 [<span data-ttu-id="9aa4a-124">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9aa4a-124">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)  
 [<span data-ttu-id="9aa4a-125">Información general sobre de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="9aa4a-125">Entity SQL Overview</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
