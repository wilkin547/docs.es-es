---
description: 'Más información acerca de: espacios de nombres (Entity SQL)'
title: Espacios de nombres (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 83991c21-60db-4af9-aca3-b416f6cae98e
ms.openlocfilehash: 70ef0021c3015fd661b42becb5371dcfd958f20f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696560"
---
# <a name="namespaces-entity-sql"></a><span data-ttu-id="59113-103">Espacios de nombres (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="59113-103">Namespaces (Entity SQL)</span></span>

[!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="59113-104">introduce espacios de nombres para evitar conflictos de nombres en los identificadores globales como los nombres de tipos, los conjuntos de entidades, las funciones, etcétera.</span><span class="sxs-lookup"><span data-stu-id="59113-104">introduces namespaces to avoid name conflicts for global identifiers such as type names, entity sets, functions, and so on.</span></span> <span data-ttu-id="59113-105">La compatibilidad con el espacio de nombres en [!INCLUDE[esql](../../../../../../includes/esql-md.md)] es similar a la compatibilidad con el espacio de nombres en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="59113-105">The namespace support in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] is similar to the namespace support in the .NET Framework.</span></span>  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="59113-106">proporciona dos formas de cláusula USING: espacios de nombres completos, a los que se proporciona un alias más breve, y espacios no completos, según se ilustra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59113-106">provides two forms of the USING clause: qualified namespaces (where a shorter alias is provided for the namespace), and unqualified namespaces, as illustrated in the following example:</span></span>  
  
 `USING System.Data;`  
  
 `USING tsql = System.Data;`  
  
## <a name="name-resolution-rules"></a><span data-ttu-id="59113-107">Reglas de la resolución de nombres</span><span class="sxs-lookup"><span data-stu-id="59113-107">Name Resolution Rules</span></span>  

 <span data-ttu-id="59113-108">Si un identificador no se puede resolver en los ámbitos locales, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta localizar el nombre en los ámbitos globales (los espacios de nombres).</span><span class="sxs-lookup"><span data-stu-id="59113-108">If an identifier cannot be resolved in the local scopes, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to locate the name in the global scopes (the namespaces).</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="59113-109">primero intenta buscar la coincidencia del identificador (prefijo) con uno de los espacios de nombres completos.</span><span class="sxs-lookup"><span data-stu-id="59113-109">first tries to match the identifier (prefix) with one of the qualified namespaces.</span></span> <span data-ttu-id="59113-110">Si hay una coincidencia, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta resolver el resto del identificador en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="59113-110">If there is a match, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to resolve the rest of the identifier in the specified namespace.</span></span> <span data-ttu-id="59113-111">Si no se encuentra ninguna coincidencia, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="59113-111">If no match is found, an exception is thrown.</span></span>  
  
 <span data-ttu-id="59113-112">A continuación, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] intenta buscar en todos los espacios de nombres incompletos (especificados en el prólogo) del identificador.</span><span class="sxs-lookup"><span data-stu-id="59113-112">Next, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] tries to search all unqualified namespaces (specified in the prolog) for the identifier.</span></span> <span data-ttu-id="59113-113">Si el identificador se puede encontrar en un espacio de nombres exactamente, se devuelve esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="59113-113">If the identifier can be located in exactly one namespace, that location is returned.</span></span> <span data-ttu-id="59113-114">Si hay una coincidencia con ese identificador en más de un espacio de nombres, se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="59113-114">If more than one namespace has a match for that identifier, an exception is thrown.</span></span> <span data-ttu-id="59113-115">Si no se puede identificar ningún espacio de nombres para el identificador, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] pasa el nombre al siguiente ámbito saliente ( <xref:System.Data.Common.DbCommand> el <xref:System.Data.Common.DbConnection> objeto o), como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="59113-115">If no namespace can be identified for the identifier, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] passes the name onto the next outward scope (the <xref:System.Data.Common.DbCommand> or <xref:System.Data.Common.DbConnection> object), as illustrated in the following example:</span></span>  
  
```sql  
SELECT TREAT(p AS NamespaceName.Employee)  
FROM ContainerName.Person AS p  
WHERE p IS OF (NamespaceName.Employee)  
```  
  
## <a name="differences-from-the-net-framework"></a><span data-ttu-id="59113-116">Diferencias con .NET Framework</span><span class="sxs-lookup"><span data-stu-id="59113-116">Differences from the .NET Framework</span></span>  

 <span data-ttu-id="59113-117">En el .NET Framework, puede usar espacios de nombres parcialmente calificados.</span><span class="sxs-lookup"><span data-stu-id="59113-117">In the .NET Framework, you can use partially qualified namespaces.</span></span> [!INCLUDE[esql](../../../../../../includes/esql-md.md)] <span data-ttu-id="59113-118">no permite esto.</span><span class="sxs-lookup"><span data-stu-id="59113-118">does not allow this.</span></span>  
  
## <a name="adonet-usage"></a><span data-ttu-id="59113-119">Uso de ADO.NET</span><span class="sxs-lookup"><span data-stu-id="59113-119">ADO.NET Usage</span></span>  

 <span data-ttu-id="59113-120">Las consultas se expresan a través de objetos <xref:System.Data.Common.DbCommand> de ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="59113-120">Queries are expressed through ADO.NET <xref:System.Data.Common.DbCommand> objects.</span></span> <span data-ttu-id="59113-121">Los objetos <xref:System.Data.Common.DbCommand> se pueden generar sobre los objetos <xref:System.Data.Common.DbConnection>.</span><span class="sxs-lookup"><span data-stu-id="59113-121"><xref:System.Data.Common.DbCommand> objects can be built over <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="59113-122">Los espacios de nombres también se pueden especificar como parte de los objetos <xref:System.Data.Common.DbCommand> y <xref:System.Data.Common.DbConnection>.</span><span class="sxs-lookup"><span data-stu-id="59113-122">Namespaces can also be specified as part of the <xref:System.Data.Common.DbCommand> and <xref:System.Data.Common.DbConnection> objects.</span></span> <span data-ttu-id="59113-123">Si [!INCLUDE[esql](../../../../../../includes/esql-md.md)] no puede resolver un identificador dentro de la propia consulta, se sondearán los espacios de nombres externos (según reglas similares).</span><span class="sxs-lookup"><span data-stu-id="59113-123">If [!INCLUDE[esql](../../../../../../includes/esql-md.md)] cannot resolve an identifier within the query itself, the external namespaces are probed (based on similar rules).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="59113-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="59113-124">See also</span></span>

- [<span data-ttu-id="59113-125">Referencia de Entity SQL</span><span class="sxs-lookup"><span data-stu-id="59113-125">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="59113-126">Información general sobre Entity SQL</span><span class="sxs-lookup"><span data-stu-id="59113-126">Entity SQL Overview</span></span>](entity-sql-overview.md)
