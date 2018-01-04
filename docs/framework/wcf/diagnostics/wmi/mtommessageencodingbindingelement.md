---
title: MtomMessageEncodingBindingElement
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4a9c6c3d-e561-4b2d-a693-7e84bdd3534a
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3cc36d7daed1a2cfaf050cbfe9661951117ff66d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="mtommessageencodingbindingelement"></a><span data-ttu-id="3cdbb-102">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3cdbb-102">MtomMessageEncodingBindingElement</span></span>
<span data-ttu-id="3cdbb-103">MtomMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="3cdbb-103">MtomMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3cdbb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3cdbb-104">Syntax</span></span>  
  
```  
class MtomMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="3cdbb-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3cdbb-105">Methods</span></span>  
 <span data-ttu-id="3cdbb-106">La clase MtomMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="3cdbb-106">The MtomMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="3cdbb-107">Propiedades</span><span class="sxs-lookup"><span data-stu-id="3cdbb-107">Properties</span></span>  
 <span data-ttu-id="3cdbb-108">La clase MtomMessageEncodingBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="3cdbb-108">The MtomMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="3cdbb-109">Codificación</span><span class="sxs-lookup"><span data-stu-id="3cdbb-109">Encoding</span></span>  
 <span data-ttu-id="3cdbb-110">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="3cdbb-110">Data type: string</span></span>  
  
 <span data-ttu-id="3cdbb-111">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3cdbb-111">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3cdbb-112">El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="3cdbb-112">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="3cdbb-113">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="3cdbb-113">MaxReadPoolSize</span></span>  
 <span data-ttu-id="3cdbb-114">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="3cdbb-114">Data type: sint32</span></span>  
  
 <span data-ttu-id="3cdbb-115">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3cdbb-115">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3cdbb-116">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="3cdbb-116">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="3cdbb-117">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="3cdbb-117">MaxWritePoolSize</span></span>  
 <span data-ttu-id="3cdbb-118">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="3cdbb-118">Data type: sint32</span></span>  
  
 <span data-ttu-id="3cdbb-119">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3cdbb-119">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3cdbb-120">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="3cdbb-120">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="3cdbb-121">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3cdbb-121">ReaderQuotas</span></span>  
 <span data-ttu-id="3cdbb-122">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="3cdbb-122">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="3cdbb-123">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="3cdbb-123">Access type: Read-only</span></span>  
  
 <span data-ttu-id="3cdbb-124">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="3cdbb-124">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3cdbb-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3cdbb-125">Requirements</span></span>  
  
|<span data-ttu-id="3cdbb-126">MOF</span><span class="sxs-lookup"><span data-stu-id="3cdbb-126">MOF</span></span>|<span data-ttu-id="3cdbb-127">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="3cdbb-127">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="3cdbb-128">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="3cdbb-128">Namespace</span></span>|<span data-ttu-id="3cdbb-129">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="3cdbb-129">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="3cdbb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3cdbb-130">See Also</span></span>  
 <xref:System.ServiceModel.Channels.MtomMessageEncodingBindingElement>
