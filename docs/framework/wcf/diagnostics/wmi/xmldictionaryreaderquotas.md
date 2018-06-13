---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 78914d52a9e57fe2e48adcfc0d7b6f911a0d8b3a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33487833"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="42374-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="42374-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="42374-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="42374-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42374-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42374-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="42374-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="42374-105">Methods</span></span>  
 <span data-ttu-id="42374-106">La clase XmlDictionaryReaderQuotas no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="42374-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="42374-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="42374-107">Properties</span></span>  
 <span data-ttu-id="42374-108">La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="42374-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="42374-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="42374-109">MaxArrayLength</span></span>  
 <span data-ttu-id="42374-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="42374-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="42374-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="42374-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42374-112">La Longitud máxima permitida de la matriz.</span><span class="sxs-lookup"><span data-stu-id="42374-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="42374-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="42374-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="42374-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="42374-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="42374-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="42374-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42374-116">El máximo permitido de bytes devueltos para cada lectura.</span><span class="sxs-lookup"><span data-stu-id="42374-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="42374-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="42374-117">MaxDepth</span></span>  
 <span data-ttu-id="42374-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="42374-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="42374-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="42374-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42374-120">La profundidad de nodo anidada máxima por cada lectura.</span><span class="sxs-lookup"><span data-stu-id="42374-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="42374-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="42374-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="42374-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="42374-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="42374-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="42374-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42374-124">Los caracteres máximos permitidos en un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="42374-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="42374-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="42374-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="42374-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="42374-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="42374-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="42374-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="42374-128">Los caracteres máximos permitidos en contenido de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="42374-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="42374-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42374-129">Requirements</span></span>  
  
|<span data-ttu-id="42374-130">MOF</span><span class="sxs-lookup"><span data-stu-id="42374-130">MOF</span></span>|<span data-ttu-id="42374-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="42374-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="42374-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="42374-132">Namespace</span></span>|<span data-ttu-id="42374-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="42374-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42374-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="42374-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
