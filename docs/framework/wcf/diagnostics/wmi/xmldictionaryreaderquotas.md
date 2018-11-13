---
title: XmlDictionaryReaderQuotas
ms.date: 03/30/2017
ms.assetid: 9b4ca8b4-0a89-4758-97ab-528a8ce18f07
ms.openlocfilehash: 9bc519509b00383be333ac605688950d2709117c
ms.sourcegitcommit: 4bca8f7e172fd019ef437a4803bf5895c6bc4781
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/03/2018
ms.locfileid: "50980536"
---
# <a name="xmldictionaryreaderquotas"></a><span data-ttu-id="bcb09-102">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="bcb09-102">XmlDictionaryReaderQuotas</span></span>
<span data-ttu-id="bcb09-103">XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="bcb09-103">XmlDictionaryReaderQuotas</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bcb09-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bcb09-104">Syntax</span></span>  
  
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
  
## <a name="methods"></a><span data-ttu-id="bcb09-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="bcb09-105">Methods</span></span>  
 <span data-ttu-id="bcb09-106">La clase XmlDictionaryReaderQuotas no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="bcb09-106">The XmlDictionaryReaderQuotas class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="bcb09-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="bcb09-107">Properties</span></span>  
 <span data-ttu-id="bcb09-108">La clase XmlDictionaryReaderQuotas tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="bcb09-108">The XmlDictionaryReaderQuotas class has the following properties:</span></span>  
  
### <a name="maxarraylength"></a><span data-ttu-id="bcb09-109">MaxArrayLength</span><span class="sxs-lookup"><span data-stu-id="bcb09-109">MaxArrayLength</span></span>  
 <span data-ttu-id="bcb09-110">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bcb09-110">Data type: sint32</span></span>  
  
 <span data-ttu-id="bcb09-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bcb09-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcb09-112">La Longitud máxima permitida de la matriz.</span><span class="sxs-lookup"><span data-stu-id="bcb09-112">The maximum allowed array length.</span></span>  
  
### <a name="maxbytesperread"></a><span data-ttu-id="bcb09-113">MaxBytesPerRead</span><span class="sxs-lookup"><span data-stu-id="bcb09-113">MaxBytesPerRead</span></span>  
 <span data-ttu-id="bcb09-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bcb09-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="bcb09-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bcb09-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcb09-116">El máximo permitido de bytes devueltos para cada lectura.</span><span class="sxs-lookup"><span data-stu-id="bcb09-116">The maximum allowed bytes returned for each read.</span></span>  
  
### <a name="maxdepth"></a><span data-ttu-id="bcb09-117">MaxDepth</span><span class="sxs-lookup"><span data-stu-id="bcb09-117">MaxDepth</span></span>  
 <span data-ttu-id="bcb09-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bcb09-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="bcb09-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bcb09-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcb09-120">La profundidad de nodo anidada máxima por cada lectura.</span><span class="sxs-lookup"><span data-stu-id="bcb09-120">The maximum nested node depth for each read.</span></span>  
  
### <a name="maxnametablecharcount"></a><span data-ttu-id="bcb09-121">MaxNameTableCharCount</span><span class="sxs-lookup"><span data-stu-id="bcb09-121">MaxNameTableCharCount</span></span>  
 <span data-ttu-id="bcb09-122">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bcb09-122">Data type: sint32</span></span>  
  
 <span data-ttu-id="bcb09-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bcb09-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcb09-124">Los caracteres máximos permitidos en un nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="bcb09-124">The maximum characters allowed in a table name.</span></span>  
  
### <a name="maxstringcontentlength"></a><span data-ttu-id="bcb09-125">MaxStringContentLength</span><span class="sxs-lookup"><span data-stu-id="bcb09-125">MaxStringContentLength</span></span>  
 <span data-ttu-id="bcb09-126">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="bcb09-126">Data type: sint32</span></span>  
  
 <span data-ttu-id="bcb09-127">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="bcb09-127">Access type: Read-only</span></span>  
  
 <span data-ttu-id="bcb09-128">Los caracteres máximos permitidos en contenido de elemento XML.</span><span class="sxs-lookup"><span data-stu-id="bcb09-128">The maximum characters allowed in XML element content.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bcb09-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bcb09-129">Requirements</span></span>  
  
|<span data-ttu-id="bcb09-130">MOF</span><span class="sxs-lookup"><span data-stu-id="bcb09-130">MOF</span></span>|<span data-ttu-id="bcb09-131">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="bcb09-131">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="bcb09-132">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="bcb09-132">Namespace</span></span>|<span data-ttu-id="bcb09-133">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="bcb09-133">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bcb09-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="bcb09-134">See Also</span></span>  
 <xref:System.Xml.XmlDictionaryReaderQuotas>  
 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>
