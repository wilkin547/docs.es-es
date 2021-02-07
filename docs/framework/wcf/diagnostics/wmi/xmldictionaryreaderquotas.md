---
description: 'Más información sobre: XmlDictionaryReaderQuotas'
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: d1450051e7107e9b92f848d26e6b182bfd2f2340
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756869"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="59dcb-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="59dcb-103">XmlDictionaryReaderQuotas</span></span>

<span data-ttu-id="59dcb-104">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="59dcb-104">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59dcb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="59dcb-105">Syntax</span></span>  
  
```csharp
class XmlDictionaryReaderQuotas  
{  
  sint32 MaxArrayLength;  
  sint32 MaxBytesPerRead;  
  sint32 MaxDepth;  
  sint32 MaxNameTableCharCount;  
  sint32 MaxStringContentLength;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="59dcb-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="59dcb-106">Methods</span></span>  

 <span data-ttu-id="59dcb-107">La clase XmlDictionaryReaderQuotas no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="59dcb-107">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="59dcb-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="59dcb-108">Properties</span></span>  

 <span data-ttu-id="59dcb-109">La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="59dcb-109">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="59dcb-110">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="59dcb-110">MaxArrayLength</span></span>  

 <span data-ttu-id="59dcb-111">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="59dcb-111">Data type: sint32</span></span>  
  
 <span data-ttu-id="59dcb-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="59dcb-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59dcb-113">La Longitud máxima permitida de la matriz.</span><span class="sxs-lookup"><span data-stu-id="59dcb-113">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="59dcb-114">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="59dcb-114">MaxBytesPerRead</span></span>  

 <span data-ttu-id="59dcb-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="59dcb-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="59dcb-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="59dcb-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59dcb-117">El máximo permitido de bytes devueltos para cada lectura.</span><span class="sxs-lookup"><span data-stu-id="59dcb-117">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="59dcb-118">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="59dcb-118">MaxDepth</span></span>  

 <span data-ttu-id="59dcb-119">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="59dcb-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="59dcb-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="59dcb-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59dcb-121">La profundidad de nodo anidada máxima por cada lectura.</span><span class="sxs-lookup"><span data-stu-id="59dcb-121">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="59dcb-122">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="59dcb-122">MaxNameTableCharCount</span></span>  

 <span data-ttu-id="59dcb-123">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="59dcb-123">Data type: sint32</span></span>  
  
 <span data-ttu-id="59dcb-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="59dcb-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59dcb-125">Los caracteres máximos permitidos en un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="59dcb-125">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="59dcb-126">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="59dcb-126">MaxStringContentLength</span></span>  

 <span data-ttu-id="59dcb-127">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="59dcb-127">Data type: sint32</span></span>  
  
 <span data-ttu-id="59dcb-128">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="59dcb-128">Access type: Read-only</span></span>  
  
 <span data-ttu-id="59dcb-129">Los caracteres máximos permitidos en contenido de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="59dcb-129">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59dcb-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="59dcb-130">Requirements</span></span>  
  
|<span data-ttu-id="59dcb-131">MOF</span><span class="sxs-lookup"><span data-stu-id="59dcb-131">MOF</span></span>|<span data-ttu-id="59dcb-132">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="59dcb-132">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="59dcb-133">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="59dcb-133">Namespace</span></span>|<span data-ttu-id="59dcb-134">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="59dcb-134">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="59dcb-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="59dcb-135">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
