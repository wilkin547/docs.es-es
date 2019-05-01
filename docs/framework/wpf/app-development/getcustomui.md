---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: 30084143949d2243fd310448c52e6b861505ad66
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61947971"
---
# <a name="getcustomui"></a><span data-ttu-id="e0c13-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="e0c13-102">GetCustomUI</span></span>
<span data-ttu-id="e0c13-103">Lo llama PresentationHost.exe para obtener mensajes de error y progreso personalizado desde el host, si se implementa.</span><span class="sxs-lookup"><span data-stu-id="e0c13-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0c13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0c13-104">Syntax</span></span>  
  
```  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0c13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0c13-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="e0c13-106">[out] Un puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="e0c13-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="e0c13-107">[out] El nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host, preferiblemente un [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] de archivos con <xref:System.Windows.Controls.Page> es su elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="e0c13-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="e0c13-108">Esta clase reside en el ensamblado especificado por `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="e0c13-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="e0c13-109">[out] Un puntero al ensamblado que contiene la interfaz de usuario de error proporcionado por el host.</span><span class="sxs-lookup"><span data-stu-id="e0c13-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="e0c13-110">[out] El nombre de la clase que es el usuario de error proporcionado por el host de la interfaz, preferiblemente un archivo XAML con <xref:System.Windows.Controls.Page> es su elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="e0c13-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="e0c13-111">Esta clase reside en el ensamblado especificado por `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="e0c13-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e0c13-112">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e0c13-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="e0c13-113">HRESULT: ignorado.</span><span class="sxs-lookup"><span data-stu-id="e0c13-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0c13-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0c13-114">Remarks</span></span>  
 <span data-ttu-id="e0c13-115">Una aplicación host puede tener un tema concreto que es posible que no cumplen interfaces de usuario predeterminada del PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="e0c13-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="e0c13-116">Si este es el caso, puede implementar la aplicación host [GetCustomUI](getcustomui.md) para devolver las interfaces de usuario de progreso y error a PresentationHost.exe.</span><span class="sxs-lookup"><span data-stu-id="e0c13-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="e0c13-117">PresentationHost.exe siempre llamará [GetCustomUI](getcustomui.md) antes de usar sus interfaces de usuario de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e0c13-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="e0c13-118">Esta función se llama una vez durante la inicialización de PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="e0c13-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0c13-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0c13-119">See also</span></span>

- [<span data-ttu-id="e0c13-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="e0c13-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
