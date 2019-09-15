---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: a9c4c9d597f5cc1b172213d49a3dd5b8f1c1f671
ms.sourcegitcommit: 005980b14629dfc193ff6cdc040800bc75e0a5a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2019
ms.locfileid: "70991379"
---
# <a name="getcustomui"></a><span data-ttu-id="e4c01-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="e4c01-102">GetCustomUI</span></span>
<span data-ttu-id="e4c01-103">Lo llama PresentationHost. exe para obtener los mensajes de error y de progreso personalizados del host, si se implementan.</span><span class="sxs-lookup"><span data-stu-id="e4c01-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4c01-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e4c01-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4c01-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e4c01-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="e4c01-106">enuncia Puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="e4c01-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="e4c01-107">enuncia El nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] , preferiblemente <xref:System.Windows.Controls.Page> un archivo con es su elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="e4c01-107">[out] The name of the class that is the host-supplied progress user interface, preferably a [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="e4c01-108">Esta clase reside en el ensamblado especificado por `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="e4c01-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="e4c01-109">enuncia Puntero al ensamblado que contiene la interfaz de usuario de error proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="e4c01-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="e4c01-110">enuncia El nombre de la clase que es la interfaz de usuario de error proporcionada por el host, preferiblemente un <xref:System.Windows.Controls.Page> archivo XAML con es su elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="e4c01-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="e4c01-111">Esta clase reside en el ensamblado especificado por `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="e4c01-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="e4c01-112">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e4c01-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="e4c01-113">HRESULT: ignorado.</span><span class="sxs-lookup"><span data-stu-id="e4c01-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4c01-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e4c01-114">Remarks</span></span>  
 <span data-ttu-id="e4c01-115">Una aplicación host puede tener un tema específico del que es posible que las interfaces de usuario predeterminadas de PresentationHost. exe no se ajusten a.</span><span class="sxs-lookup"><span data-stu-id="e4c01-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="e4c01-116">En este caso, la aplicación host puede implementar [GetCustomUI](getcustomui.md) para devolver interfaces de usuario de progreso y error a PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="e4c01-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="e4c01-117">PresentationHost. exe siempre llama a [GetCustomUI](getcustomui.md) antes de usar sus interfaces de usuario predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="e4c01-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="e4c01-118">Esta función se llama una vez durante la inicialización de PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="e4c01-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4c01-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e4c01-119">See also</span></span>

- [<span data-ttu-id="e4c01-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="e4c01-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
