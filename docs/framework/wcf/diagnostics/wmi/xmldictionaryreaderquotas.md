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
ms.openlocfilehash: 06c0ff11752ae1030e574182cfb825fb87ddc8c7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="f5415-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f5415-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="f5415-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="f5415-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f5415-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f5415-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="f5415-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f5415-105">Methods</span></span>  
 <span data-ttu-id="f5415-106">La clase XmlDictionaryReaderQuotas no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="f5415-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="f5415-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="f5415-107">Properties</span></span>  
 <span data-ttu-id="f5415-108">La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="f5415-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="f5415-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="f5415-109">MaxArrayLength</span></span>  
 <span data-ttu-id="f5415-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f5415-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="f5415-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f5415-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5415-112">La Longitud máxima permitida de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f5415-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="f5415-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="f5415-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="f5415-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f5415-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="f5415-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f5415-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5415-116">El máximo permitido de bytes devueltos para cada lectura.</span><span class="sxs-lookup"><span data-stu-id="f5415-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="f5415-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="f5415-117">MaxDepth</span></span>  
 <span data-ttu-id="f5415-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f5415-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="f5415-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f5415-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5415-120">La profundidad de nodo anidada máxima por cada lectura.</span><span class="sxs-lookup"><span data-stu-id="f5415-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="f5415-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="f5415-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="f5415-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f5415-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="f5415-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f5415-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5415-124">Los caracteres máximos permitidos en un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="f5415-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="f5415-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="f5415-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="f5415-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="f5415-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="f5415-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="f5415-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="f5415-128">Los caracteres máximos permitidos en contenido de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="f5415-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f5415-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f5415-129">Requirements</span></span>  
  
|<span data-ttu-id="f5415-130">MOF</span><span class="sxs-lookup"><span data-stu-id="f5415-130">MOF</span></span>|<span data-ttu-id="f5415-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="f5415-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="f5415-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="f5415-132">Namespace</span></span>|<span data-ttu-id="f5415-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="f5415-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5415-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="f5415-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
