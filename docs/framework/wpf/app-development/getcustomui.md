---
title: GetCustomUI
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 88c2873a5929e25335b0c6ef64f8121e31177ab4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getcustomui"></a><span data-ttu-id="b2d76-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="b2d76-102">GetCustomUI</span></span>
<span data-ttu-id="b2d76-103">Lo llama PresentationHost.exe obtener personalizados de progreso y mensajes de error desde el host, si implementa.</span><span class="sxs-lookup"><span data-stu-id="b2d76-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2d76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b2d76-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b2d76-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b2d76-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="b2d76-106">[out] Un puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="b2d76-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="b2d76-107">[out] El nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host, preferiblemente una [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] de archivos con <xref:System.Windows.Controls.Page> es su elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b2d76-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="b2d76-108">Esta clase reside en el ensamblado especificado por `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b2d76-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="b2d76-109">[out] Un puntero al ensamblado que contiene la interfaz de usuario de error proporcionado por el host.</span><span class="sxs-lookup"><span data-stu-id="b2d76-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="b2d76-110">[out] El nombre de la clase que es el usuario de error proporcionado por el host de la interfaz, preferentemente un archivo XAML con <xref:System.Windows.Controls.Page> es su elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="b2d76-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="b2d76-111">Esta clase reside en el ensamblado especificado por `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="b2d76-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b2d76-112">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b2d76-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="b2d76-113">HRESULT: pasa por alto.</span><span class="sxs-lookup"><span data-stu-id="b2d76-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2d76-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b2d76-114">Remarks</span></span>  
 <span data-ttu-id="b2d76-115">Una aplicación host puede tener un tema específico que interfaces de usuario predeterminadas del PresentationHost.exe no pueden cumplir.</span><span class="sxs-lookup"><span data-stu-id="b2d76-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="b2d76-116">Si este es el caso, puede implementar la aplicación host [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) para devolver las interfaces de usuario de progreso y error a PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="b2d76-116">If this is the case, the host application can implement [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="b2d76-117">PresentationHost.exe siempre llamará [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) antes de utilizar sus interfaces de usuario de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b2d76-117">PresentationHost.exe will always call [GetCustomUI](../../../../docs/framework/wpf/app-development/getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="b2d76-118">Esta función se invoca una vez durante la inicialización de PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="b2d76-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2d76-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b2d76-119">See Also</span></span>  
 [<span data-ttu-id="b2d76-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="b2d76-120">IWpfHostSupport</span></span>](../../../../docs/framework/wpf/app-development/iwpfhostsupport.md)
