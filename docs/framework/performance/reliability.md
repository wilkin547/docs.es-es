---
title: Confiabilidad
ms.date: 03/30/2017
helpviewer_keywords:
- SQL Server [.NET Framework]
- managed code, reliability
- reliability [.NET Framework]
- writing reliable code
- code, reliability
ms.assetid: 294aa306-0afe-4cbe-b397-86ba9f1860f8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: acb84c6617cdffabfe276895f81e7df2b04bb8bb
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71046236"
---
# <a name="reliability"></a><span data-ttu-id="b5ab2-102">Confiabilidad</span><span class="sxs-lookup"><span data-stu-id="b5ab2-102">Reliability</span></span>
<span data-ttu-id="b5ab2-103">Es importante que el código que se ejecuta en entornos de servidor, como SQL Server, proteja contra las excepciones asincrónicas.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-103">It is important that code executing in server environments such as SQL Server protect against asynchronous exceptions.</span></span> <span data-ttu-id="b5ab2-104">Como ya se ha dicho, la confiabilidad no es específica de SQL Server, sino de la escritura de código confiable para cualquier host que se ejecute en un entorno de .NET Framework versión 2.0.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-104">Reliability, as discussed here, is not specific to SQL Server but to writing reliable code for any host executing in a .NET Framework version 2.0 environment.</span></span> <span data-ttu-id="b5ab2-105">Pero SQL Server es el primer servicio que realiza un amplio uso de las nuevas características de confiabilidad de la versión 2.0, razón por la que se usa como ejemplo.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-105">However, SQL Server is the first service making extensive use of the new reliability features of version 2.0, so it is used as an example.</span></span>  
  
 <span data-ttu-id="b5ab2-106">El código que se ejecuta en SQL Server debe tratar con directrices de confiabilidad más estrictas que otros entornos de servidor.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-106">Code running in SQL Server must deal with more stringent reliability guidelines than other server environments.</span></span> <span data-ttu-id="b5ab2-107">Esto se debe a que SQL Server siempre funciona en el límite del consumo de recursos.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-107">This is due to SQL Server’s steady operation at the edge of resource consumption.</span></span>  <span data-ttu-id="b5ab2-108">No es raro que se produzcan excepciones <xref:System.OutOfMemoryException> y <xref:System.Threading.ThreadAbortException> en el entorno de SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-108"><xref:System.OutOfMemoryException> and <xref:System.Threading.ThreadAbortException> exceptions are not uncommon in the SQL Server environment.</span></span> <span data-ttu-id="b5ab2-109">En general, estas instrucciones se centran menos en la confiabilidad y más en permitir que el código administrado de plena confianza genere un error ante un reciclaje de nivel <xref:System.AppDomain>, que es la principal manera que tiene el servidor de mantener la coherencia y la disponibilidad.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-109">These guidelines in general are focused less on reliability and more on allowing fully trusted managed code to fail gracefully in the face of <xref:System.AppDomain>-level recycling, which is the primary way the server maintains consistency and availability.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="b5ab2-110">En esta sección</span><span class="sxs-lookup"><span data-stu-id="b5ab2-110">In This Section</span></span>  
 [<span data-ttu-id="b5ab2-111">Programación en SQL Server y atributos de protección de host</span><span class="sxs-lookup"><span data-stu-id="b5ab2-111">SQL Server Programming and Host Protection Attributes</span></span>](sql-server-programming-and-host-protection-attributes.md)  
 <span data-ttu-id="b5ab2-112">Describe la manera en que SQL Server usa el atributo <xref:System.Security.Permissions.HostProtectionAttribute> para restringir la ejecución de código administrado.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-112">Describes how the <xref:System.Security.Permissions.HostProtectionAttribute> attribute is used by SQL Server to restrict the execution of managed code.</span></span>  
  
 [<span data-ttu-id="b5ab2-113">Reliability Best Practices (Procedimientos recomendados para la confiabilidad)</span><span class="sxs-lookup"><span data-stu-id="b5ab2-113">Reliability Best Practices</span></span>](reliability-best-practices.md)  
 <span data-ttu-id="b5ab2-114">Proporciona instrucciones para escribir código que cumpla los requisitos de confiabilidad.</span><span class="sxs-lookup"><span data-stu-id="b5ab2-114">Provides guidelines for writing code that meets reliability requirements.</span></span>  
  
 [<span data-ttu-id="b5ab2-115">Regiones de ejecución restringidas</span><span class="sxs-lookup"><span data-stu-id="b5ab2-115">Constrained Execution Regions</span></span>](constrained-execution-regions.md)  
 <span data-ttu-id="b5ab2-116">Describe el funcionamiento y el comportamiento de las regiones de ejecución restringidas (CER).</span><span class="sxs-lookup"><span data-stu-id="b5ab2-116">Describes the function and behavior of constrained execution regions (CERs).</span></span>  
  
## <a name="reference"></a><span data-ttu-id="b5ab2-117">Referencia</span><span class="sxs-lookup"><span data-stu-id="b5ab2-117">Reference</span></span>  
 <xref:System.Security.Permissions.HostProtectionAttribute>  
  
 <xref:System.Security.Permissions.HostProtectionResource>
