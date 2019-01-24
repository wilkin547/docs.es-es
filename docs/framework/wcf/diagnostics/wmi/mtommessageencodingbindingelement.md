---
title: MtomMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
ms.openlocfilehash: ad4f2cc3b03111854d10d6a1c1128f090a629a07
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54490987"
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="c55d8-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="c55d8-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="c55d8-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="c55d8-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c55d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c55d8-104">Syntax</span></span>  
  
```csharp
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="c55d8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c55d8-105">Methods</span></span>  
 <span data-ttu-id="c55d8-106">La clase MtomMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="c55d8-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="c55d8-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="c55d8-107">Properties</span></span>  
 <span data-ttu-id="c55d8-108">La clase MtomMessageEncodingBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="c55d8-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="c55d8-109">Codificación</span><span class="sxs-lookup"><span data-stu-id="c55d8-109">Encoding</span></span>  
 <span data-ttu-id="c55d8-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="c55d8-110">Data type: string</span></span>  
  
 <span data-ttu-id="c55d8-111">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="c55d8-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c55d8-112">El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="c55d8-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="c55d8-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="c55d8-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="c55d8-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c55d8-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="c55d8-115">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="c55d8-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c55d8-116">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="c55d8-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="c55d8-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="c55d8-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="c55d8-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="c55d8-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="c55d8-119">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="c55d8-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c55d8-120">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="c55d8-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="c55d8-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="c55d8-121">ReaderQuotas</span></span>  
 <span data-ttu-id="c55d8-122">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="c55d8-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="c55d8-123">Tipo de acceso: De sólo lectura</span><span class="sxs-lookup"><span data-stu-id="c55d8-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="c55d8-124">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="c55d8-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c55d8-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c55d8-125">Requirements</span></span>  
  
|<span data-ttu-id="c55d8-126">MOF</span><span class="sxs-lookup"><span data-stu-id="c55d8-126">MOF</span></span>|<span data-ttu-id="c55d8-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="c55d8-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="c55d8-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="c55d8-128">Namespace</span></span>|<span data-ttu-id="c55d8-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="c55d8-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c55d8-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="c55d8-130">See also</span></span>
- <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
