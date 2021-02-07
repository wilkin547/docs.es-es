---
description: 'Más información sobre: Message. WriteStartHeaders (método)'
title: Método Message. WriteStartHeaders (System. ServiceModel. Channels)
ms.date: 11/01/2019
topic_type:
- apiref
api_name:
- System.ServiceModel.Channels.Message.WriteStartHeaders
api_location:
- system.servicemodel.dll
api_type:
- Assembly
ms.openlocfilehash: 20cadf5f1eecf6d8e02c5dc4597889abaef4ec36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699368"
---
# <a name="messagewritestartheaders-method"></a><span data-ttu-id="d601b-103">Message. WriteStartHeaders (método)</span><span class="sxs-lookup"><span data-stu-id="d601b-103">Message.WriteStartHeaders Method</span></span>

<span data-ttu-id="d601b-104">Escribe el encabezado de inicio en un archivo XML llamando al <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> método.</span><span class="sxs-lookup"><span data-stu-id="d601b-104">Writes the start header into an XML file by calling the <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a><span data-ttu-id="d601b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d601b-105">Parameters</span></span>

- <span data-ttu-id="d601b-106">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="d601b-106">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="d601b-107">Escritor que se usa para escribir el encabezado de inicio en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="d601b-107">The writer that is used to write the start header into an XML file.</span></span>

## <a name="remarks"></a><span data-ttu-id="d601b-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="d601b-108">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="d601b-109">El `Message.WriteStartHeaders` método es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="d601b-109">The `Message.WriteStartHeaders` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="d601b-110">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="d601b-110">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="d601b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d601b-111">Requirements</span></span>

<span data-ttu-id="d601b-112">**Espacio de nombres:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="d601b-112">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="d601b-113">**Ensamblado:** System.ServiceModel.dll</span><span class="sxs-lookup"><span data-stu-id="d601b-113">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="d601b-114">**.NET Framework versiones:** Disponible desde 3,0.</span><span class="sxs-lookup"><span data-stu-id="d601b-114">**.NET Framework versions:** Available since 3.0.</span></span>
