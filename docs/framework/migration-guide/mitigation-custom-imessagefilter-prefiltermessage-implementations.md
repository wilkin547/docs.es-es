---
title: 'Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage'
description: Obtenga información sobre la implementación IMessageFilter.PreFilterMessage personalizada que se incluye en aplicaciones de Windows Forms que tienen como destino .NET Framework 4.6.1 y versiones posteriores.
ms.date: 03/30/2017
ms.assetid: 9cf47c5b-0bb2-45df-9437-61cd7e7c2f4d
ms.openlocfilehash: 5fe7500d3ed6ff293514495df150a747e7946dda
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86475260"
---
# <a name="mitigation-custom-imessagefilterprefiltermessage-implementations"></a><span data-ttu-id="744bb-103">Mitigación: personalizar implementaciones de IMessageFilter.PreFilterMessage</span><span class="sxs-lookup"><span data-stu-id="744bb-103">Mitigation: Custom IMessageFilter.PreFilterMessage Implementations</span></span>

<span data-ttu-id="744bb-104">En las aplicaciones de Windows Forms destinadas a versiones de .NET Framework a partir de .NET Framework 4.6.1, una implementación personalizada de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> puede filtrar mensajes de forma segura al llamar al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> si la implementación de <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="744bb-104">In Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1, a custom <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation can safely filter messages when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called if the <xref:System.Windows.Forms.IMessageFilter.PreFilterMessage%2A?displayProperty=nameWithType> implementation:</span></span>

- <span data-ttu-id="744bb-105">Realiza una o dos de las siguientes acciones:</span><span class="sxs-lookup"><span data-stu-id="744bb-105">Does one or both of the following:</span></span>

  - <span data-ttu-id="744bb-106">Agregar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.AddMessageFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="744bb-106">Adds a message filter by calling the <xref:System.Windows.Forms.Application.AddMessageFilter%2A> method.</span></span>

  - <span data-ttu-id="744bb-107">Quitar un filtro de mensajes al llamar al método <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A>.</span><span class="sxs-lookup"><span data-stu-id="744bb-107">Removes a message filter by calling the <xref:System.Windows.Forms.Application.RemoveMessageFilter%2A> method.</span></span> <span data-ttu-id="744bb-108">.</span><span class="sxs-lookup"><span data-stu-id="744bb-108">method.</span></span>

- <span data-ttu-id="744bb-109">El elemento **And** proporciona mensajes mediante una llamada al método <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="744bb-109">**And** pumps messages by calling the <xref:System.Windows.Forms.Application.DoEvents%2A?displayProperty=nameWithType> method.</span></span>

## <a name="impact"></a><span data-ttu-id="744bb-110">Impacto</span><span class="sxs-lookup"><span data-stu-id="744bb-110">Impact</span></span>

<span data-ttu-id="744bb-111">Este cambio solo afecta a aplicaciones de Windows Forms que tienen como destino versiones de .NET Framework a partir de .NET Framework 4.6.1.</span><span class="sxs-lookup"><span data-stu-id="744bb-111">This change only affects Windows Forms apps that target versions of the .NET Framework starting with the .NET Framework 4.6.1.</span></span>

<span data-ttu-id="744bb-112">Para las aplicaciones de Windows Forms destinadas a las versiones anteriores de .NET Framework, en algunos casos, tales implementaciones inician una excepción <xref:System.IndexOutOfRangeException> cuando se llama al método <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="744bb-112">For Windows Forms apps that target previous versions of the .NET Framework, such implementations in some cases throw an <xref:System.IndexOutOfRangeException> exception when the <xref:System.Windows.Forms.Application.FilterMessage%2A?displayProperty=nameWithType> method is called</span></span>

## <a name="mitigation"></a><span data-ttu-id="744bb-113">Mitigación</span><span class="sxs-lookup"><span data-stu-id="744bb-113">Mitigation</span></span>

<span data-ttu-id="744bb-114">Si no quiere este cambio, las aplicaciones que tienen como destino .NET Framework 4.6.1 o una versión posterior pueden descartarlo si se agrega el siguiente valor de configuración a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="744bb-114">If this change is undesirable, apps that target the .NET Framework 4.6.1 or a later version can opt out of it by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=true" />
</runtime>
```

<span data-ttu-id="744bb-115">Además, las aplicaciones que tienen como destino versiones anteriores de .NET Framework, pero que se ejecutan en .NET Framework 4.6.1 o una versión posterior, pueden optar por recibir este comportamiento si se agrega el siguiente valor de configuración a la sección [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) del archivo de configuración de la aplicación:</span><span class="sxs-lookup"><span data-stu-id="744bb-115">In addition, apps that target previous versions of the .NET Framework but are running under the .NET Framework 4.6.1 or a later version can opt in to this behavior by adding the following configuration setting to the [\<runtime>](../configure-apps/file-schema/runtime/runtime-element.md) section of the app’s configuration file:</span></span>

```xml
<runtime>
    <AppContextSwitchOverrides value="Switch.System.Windows.Forms.DontSupportReentrantFilterMessage=false" />
</runtime>
```

## <a name="see-also"></a><span data-ttu-id="744bb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="744bb-116">See also</span></span>

- [<span data-ttu-id="744bb-117">Compatibilidad de aplicaciones</span><span class="sxs-lookup"><span data-stu-id="744bb-117">Application compatibility</span></span>](application-compatibility.md)
