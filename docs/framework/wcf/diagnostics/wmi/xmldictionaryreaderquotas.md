---
title: XmlDictionaryReaderQuotas
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 1a3afb9b8cfede60c773d146f4d1728d7fe02b75
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="551e0-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="551e0-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="551e0-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="551e0-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="551e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="551e0-104">Syntax</span></span>  
  
```  
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="551e0-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="551e0-105">Methods</span></span>  
 <span data-ttu-id="551e0-106">La clase XmlDictionaryReaderQuotas no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="551e0-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="551e0-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="551e0-107">Properties</span></span>  
 <span data-ttu-id="551e0-108">La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="551e0-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="551e0-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="551e0-109">MaxArrayLength</span></span>  
 <span data-ttu-id="551e0-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="551e0-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="551e0-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="551e0-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="551e0-112">La Longitud máxima permitida de la matriz.</span><span class="sxs-lookup"><span data-stu-id="551e0-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="551e0-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="551e0-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="551e0-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="551e0-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="551e0-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="551e0-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="551e0-116">El máximo permitido de bytes devueltos para cada lectura.</span><span class="sxs-lookup"><span data-stu-id="551e0-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="551e0-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="551e0-117">MaxDepth</span></span>  
 <span data-ttu-id="551e0-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="551e0-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="551e0-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="551e0-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="551e0-120">La profundidad de nodo anidada máxima por cada lectura.</span><span class="sxs-lookup"><span data-stu-id="551e0-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="551e0-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="551e0-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="551e0-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="551e0-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="551e0-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="551e0-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="551e0-124">Los caracteres máximos permitidos en un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="551e0-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="551e0-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="551e0-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="551e0-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="551e0-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="551e0-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="551e0-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="551e0-128">Los caracteres máximos permitidos en contenido de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="551e0-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="551e0-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="551e0-129">Requirements</span></span>  
  
|<span data-ttu-id="551e0-130">MOF</span><span class="sxs-lookup"><span data-stu-id="551e0-130">MOF</span></span>|<span data-ttu-id="551e0-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="551e0-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="551e0-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="551e0-132">Namespace</span></span>|<span data-ttu-id="551e0-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="551e0-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="551e0-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="551e0-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
