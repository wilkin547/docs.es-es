---
description: 'Más información acerca de: TextMessageEncodingBindingElement'
title: TextMessageEncodingBindingElement
ms.date: 03/30/2017
ms.assetid: 885e2d7a-3436-4093-bc5f-0a404c62acdc
ms.openlocfilehash: 9848f1660642f92c4bce3542fbd404f463b8c84d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99757350"
---
# <a name="textmessageencodingbindingelement"></a><span data-ttu-id="054ce-103">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="054ce-103">TextMessageEncodingBindingElement</span></span>

<span data-ttu-id="054ce-104">TextMessageEncodingBindingElement</span><span class="sxs-lookup"><span data-stu-id="054ce-104">TextMessageEncodingBindingElement</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="054ce-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="054ce-105">Syntax</span></span>  
  
```csharp
class TextMessageEncodingBindingElement : MessageEncodingBindingElement  
{  
  string Encoding;  
  sint32 MaxReadPoolSize;  
  sint32 MaxWritePoolSize;  
  XmlDictionaryReaderQuotas ReaderQuotas;  
};  
```  
  
## <a name="methods"></a><span data-ttu-id="054ce-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="054ce-106">Methods</span></span>  

 <span data-ttu-id="054ce-107">La clase TextMessageEncodingBindingElement no define ningún método.</span><span class="sxs-lookup"><span data-stu-id="054ce-107">The TextMessageEncodingBindingElement class does not define any methods.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="054ce-108">Propiedades</span><span class="sxs-lookup"><span data-stu-id="054ce-108">Properties</span></span>  

 <span data-ttu-id="054ce-109">La clase TextMessageEncodingBindingElement tiene las propiedades siguientes:</span><span class="sxs-lookup"><span data-stu-id="054ce-109">The TextMessageEncodingBindingElement class has the following properties:</span></span>  
  
### <a name="encoding"></a><span data-ttu-id="054ce-110">Encoding</span><span class="sxs-lookup"><span data-stu-id="054ce-110">Encoding</span></span>  

 <span data-ttu-id="054ce-111">Tipo de datos: cadena</span><span class="sxs-lookup"><span data-stu-id="054ce-111">Data type: string</span></span>  
  
 <span data-ttu-id="054ce-112">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="054ce-112">Access type: Read-only</span></span>  
  
 <span data-ttu-id="054ce-113">El codificador del juego de caracteres que se va a usar para emitir los mensajes en el enlace.</span><span class="sxs-lookup"><span data-stu-id="054ce-113">The character set encoding to be used for emitting messages on the binding.</span></span>  
  
### <a name="maxreadpoolsize"></a><span data-ttu-id="054ce-114">MaxReadPoolSize</span><span class="sxs-lookup"><span data-stu-id="054ce-114">MaxReadPoolSize</span></span>  

 <span data-ttu-id="054ce-115">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="054ce-115">Data type: sint32</span></span>  
  
 <span data-ttu-id="054ce-116">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="054ce-116">Access type: Read-only</span></span>  
  
 <span data-ttu-id="054ce-117">Entero que define cuántos mensajes pueden leerse simultáneamente sin asignar nuevos lectores.</span><span class="sxs-lookup"><span data-stu-id="054ce-117">An integer that defines how many messages can be read simultaneously without allocating new readers.</span></span>  
  
### <a name="maxwritepoolsize"></a><span data-ttu-id="054ce-118">MaxWritePoolSize</span><span class="sxs-lookup"><span data-stu-id="054ce-118">MaxWritePoolSize</span></span>  

 <span data-ttu-id="054ce-119">Tipo de datos: sint32</span><span class="sxs-lookup"><span data-stu-id="054ce-119">Data type: sint32</span></span>  
  
 <span data-ttu-id="054ce-120">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="054ce-120">Access type: Read-only</span></span>  
  
 <span data-ttu-id="054ce-121">Entero que define cuántos mensajes pueden enviarse simultáneamente sin asignar nuevos escritores.</span><span class="sxs-lookup"><span data-stu-id="054ce-121">An integer that defines how many messages can be sent simultaneously without allocating new writers.</span></span>  
  
### <a name="readerquotas"></a><span data-ttu-id="054ce-122">ReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="054ce-122">ReaderQuotas</span></span>  

 <span data-ttu-id="054ce-123">Tipo de datos: XmlDictionaryReaderQuotas</span><span class="sxs-lookup"><span data-stu-id="054ce-123">Data type: XmlDictionaryReaderQuotas</span></span>  
  
 <span data-ttu-id="054ce-124">Tipo de acceso: solo lectura</span><span class="sxs-lookup"><span data-stu-id="054ce-124">Access type: Read-only</span></span>  
  
 <span data-ttu-id="054ce-125">Las cuotas de los lectores.</span><span class="sxs-lookup"><span data-stu-id="054ce-125">The quotas of the readers.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="054ce-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="054ce-126">Requirements</span></span>  
  
|<span data-ttu-id="054ce-127">MOF</span><span class="sxs-lookup"><span data-stu-id="054ce-127">MOF</span></span>|<span data-ttu-id="054ce-128">Se declara en Servicemodel.mof.</span><span class="sxs-lookup"><span data-stu-id="054ce-128">Declared in Servicemodel.mof.</span></span>|  
|---------|-----------------------------------|  
|<span data-ttu-id="054ce-129">Espacio de nombres</span><span class="sxs-lookup"><span data-stu-id="054ce-129">Namespace</span></span>|<span data-ttu-id="054ce-130">Se define en root\ServiceModel</span><span class="sxs-lookup"><span data-stu-id="054ce-130">Defined in root\ServiceModel</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="054ce-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="054ce-131">See also</span></span>

- <xref:System.ServiceModel.Channels.TextMessageEncodingBindingElement>
