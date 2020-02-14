---
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
ms.openlocfilehash: c826e6a3b976e5705e9815586441e8a25b64f76e
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2020
ms.locfileid: "77214861"
---
# <a name="messagewritestartheaders-method"></a><span data-ttu-id="e1d13-102">Message. WriteStartHeaders (método)</span><span class="sxs-lookup"><span data-stu-id="e1d13-102">Message.WriteStartHeaders Method</span></span>

<span data-ttu-id="e1d13-103">Escribe el encabezado de inicio en un archivo XML llamando al método <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="e1d13-103">Writes the start header into an XML file by calling the <xref:System.ServiceModel.Channels.Message.OnWriteStartHeaders%2A?displayProperty=nameWithType> method.</span></span>

```csharp
internal void WriteStartHeaders(XmlDictionaryWriter writer)
```

## <a name="parameters"></a><span data-ttu-id="e1d13-104">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1d13-104">Parameters</span></span>

- <span data-ttu-id="e1d13-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span><span class="sxs-lookup"><span data-stu-id="e1d13-105">`writer` <xref:System.Xml.XmlDictionaryWriter></span></span>\
  <span data-ttu-id="e1d13-106">Escritor que se usa para escribir el encabezado de inicio en un archivo XML.</span><span class="sxs-lookup"><span data-stu-id="e1d13-106">The writer that is used to write the start header into an XML file.</span></span>

## <a name="remarks"></a><span data-ttu-id="e1d13-107">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e1d13-107">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="e1d13-108">El método `Message.WriteStartHeaders` es interno y no está diseñado para usarse directamente en el código.</span><span class="sxs-lookup"><span data-stu-id="e1d13-108">The `Message.WriteStartHeaders` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="e1d13-109">Microsoft no admite el uso de este método en una aplicación de producción bajo ninguna circunstancia.</span><span class="sxs-lookup"><span data-stu-id="e1d13-109">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1d13-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1d13-110">Requirements</span></span>

<span data-ttu-id="e1d13-111">**Espacio de nombres:** <xref:System.ServiceModel.Channels></span><span class="sxs-lookup"><span data-stu-id="e1d13-111">**Namespace:** <xref:System.ServiceModel.Channels></span></span>

<span data-ttu-id="e1d13-112">**Ensamblado:** System. ServiceModel. dll</span><span class="sxs-lookup"><span data-stu-id="e1d13-112">**Assembly:** System.ServiceModel.dll</span></span>

<span data-ttu-id="e1d13-113">**.NET Framework versiones:** Disponible desde 3,0.</span><span class="sxs-lookup"><span data-stu-id="e1d13-113">**.NET Framework versions:** Available since 3.0.</span></span>
