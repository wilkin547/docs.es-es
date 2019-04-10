---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: f1c12a0a60397a84d4e9ff0241c4182b4511af5c
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59214889"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="dafd5-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="dafd5-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="dafd5-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="dafd5-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dafd5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="dafd5-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="dafd5-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dafd5-105">Methods</span></span>  
 <span data-ttu-id="dafd5-106">La clase XmlDictionaryReaderQuotas no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="dafd5-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="dafd5-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="dafd5-107">Properties</span></span>  
 <span data-ttu-id="dafd5-108">La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="dafd5-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="dafd5-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="dafd5-109">MaxArrayLength</span></span>  
 <span data-ttu-id="dafd5-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="dafd5-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="dafd5-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="dafd5-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dafd5-112">La Longitud máxima permitida de la matriz.</span><span class="sxs-lookup"><span data-stu-id="dafd5-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="dafd5-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="dafd5-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="dafd5-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="dafd5-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="dafd5-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="dafd5-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dafd5-116">El máximo permitido de bytes devueltos para cada lectura.</span><span class="sxs-lookup"><span data-stu-id="dafd5-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="dafd5-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="dafd5-117">MaxDepth</span></span>  
 <span data-ttu-id="dafd5-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="dafd5-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="dafd5-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="dafd5-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dafd5-120">La profundidad de nodo anidada máxima por cada lectura.</span><span class="sxs-lookup"><span data-stu-id="dafd5-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="dafd5-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="dafd5-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="dafd5-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="dafd5-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="dafd5-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="dafd5-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dafd5-124">Los caracteres máximos permitidos en un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="dafd5-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="dafd5-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="dafd5-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="dafd5-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="dafd5-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="dafd5-127">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="dafd5-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="dafd5-128">Los caracteres máximos permitidos en contenido de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="dafd5-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dafd5-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dafd5-129">Requirements</span></span>  
  
|<span data-ttu-id="dafd5-130">MOF</span><span class="sxs-lookup"><span data-stu-id="dafd5-130">MOF</span></span>|<span data-ttu-id="dafd5-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="dafd5-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="dafd5-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="dafd5-132">Namespace</span></span>|<span data-ttu-id="dafd5-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="dafd5-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="dafd5-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="dafd5-134">See also</span></span>

- <xref:System.Xml.XmlDictionaryReaderQuotas>
- <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
