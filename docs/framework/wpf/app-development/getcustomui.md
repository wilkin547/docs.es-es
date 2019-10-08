---
title: GetCustomUI
ms.date: 03/30/2017
helpviewer_keywords:
- custom error messages [WPF]
ms.assetid: e55180fc-35bb-4f80-a136-772b5eb3e4e5
ms.openlocfilehash: e9ef32912c2afb3c99e46e1e14bb3daa5a2e99af
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005711"
---
# <a name="getcustomui"></a><span data-ttu-id="f53e4-102">GetCustomUI</span><span class="sxs-lookup"><span data-stu-id="f53e4-102">GetCustomUI</span></span>
<span data-ttu-id="f53e4-103">Lo llama PresentationHost. exe para obtener los mensajes de error y de progreso personalizados del host, si se implementan.</span><span class="sxs-lookup"><span data-stu-id="f53e4-103">Called by PresentationHost.exe to get custom progress and error messages from the host, if implemented.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f53e4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f53e4-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCustomUI( [out] BSTR* pwzProgressAssemblyName, [out] BSTR* pwzProgressClassName, [out] BSTR* pwzErrorAssemblyName, [out] BSTR* pwzErrorClassName );  
```  
  
## <a name="parameters"></a><span data-ttu-id="f53e4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f53e4-105">Parameters</span></span>  
 `pwzProgressAssemblyName`  
  
 <span data-ttu-id="f53e4-106">enuncia Puntero al ensamblado que contiene la interfaz de usuario de progreso proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="f53e4-106">[out] A pointer to the assembly that contains the host-supplied progress user interface.</span></span>  
  
 `pwzProgressClassName`  
  
 <span data-ttu-id="f53e4-107">enuncia El nombre de la clase que es la interfaz de usuario de progreso proporcionada por el host, preferiblemente un archivo XAML con <xref:System.Windows.Controls.Page> es su elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="f53e4-107">[out] The name of the class that is the host-supplied progress user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="f53e4-108">Esta clase reside en el ensamblado especificado por `pwzProgressAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="f53e4-108">This class resides in the assembly that is specified by `pwzProgressAssemblyName`.</span></span>  
  
 `pwzErrorAssemblyName`  
  
 <span data-ttu-id="f53e4-109">enuncia Puntero al ensamblado que contiene la interfaz de usuario de error proporcionada por el host.</span><span class="sxs-lookup"><span data-stu-id="f53e4-109">[out] A pointer to the assembly that contains the host-supplied error user interface.</span></span>  
  
 `pwzErrorClassName`  
  
 <span data-ttu-id="f53e4-110">enuncia El nombre de la clase que es la interfaz de usuario de error proporcionada por el host, preferiblemente un archivo XAML con <xref:System.Windows.Controls.Page> es el elemento de nivel superior.</span><span class="sxs-lookup"><span data-stu-id="f53e4-110">[out] The name of the class that is the host-supplied error user interface, preferably a XAML file with <xref:System.Windows.Controls.Page> is its top-level element.</span></span> <span data-ttu-id="f53e4-111">Esta clase reside en el ensamblado especificado por `pwzErrorAssemblyName`.</span><span class="sxs-lookup"><span data-stu-id="f53e4-111">This class resides in the assembly that is specified by `pwzErrorAssemblyName`.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f53e4-112">Valor de propiedad y valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f53e4-112">Property Value/Return Value</span></span>  
 <span data-ttu-id="f53e4-113">HRESULT: ignorado.</span><span class="sxs-lookup"><span data-stu-id="f53e4-113">HRESULT: Ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f53e4-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f53e4-114">Remarks</span></span>  
 <span data-ttu-id="f53e4-115">Una aplicación host puede tener un tema específico del que es posible que las interfaces de usuario predeterminadas de PresentationHost. exe no se ajusten a.</span><span class="sxs-lookup"><span data-stu-id="f53e4-115">A host application may have a specific theme that PresentationHost.exe’s default user interfaces may not conform to.</span></span> <span data-ttu-id="f53e4-116">En este caso, la aplicación host puede implementar [GetCustomUI](getcustomui.md) para devolver interfaces de usuario de progreso y error a PresentationHost. exe.</span><span class="sxs-lookup"><span data-stu-id="f53e4-116">If this is the case, the host application can implement [GetCustomUI](getcustomui.md) to return progress and error user interfaces to PresentationHost.exe.</span></span> <span data-ttu-id="f53e4-117">PresentationHost. exe siempre llama a [GetCustomUI](getcustomui.md) antes de usar sus interfaces de usuario predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="f53e4-117">PresentationHost.exe will always call [GetCustomUI](getcustomui.md) before using its default user interfaces.</span></span>  
  
 <span data-ttu-id="f53e4-118">Esta función se llama una vez durante la inicialización de PresentationHost.</span><span class="sxs-lookup"><span data-stu-id="f53e4-118">This function is called once during PresentationHost’s initialization.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f53e4-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f53e4-119">See also</span></span>

- [<span data-ttu-id="f53e4-120">IWpfHostSupport</span><span class="sxs-lookup"><span data-stu-id="f53e4-120">IWpfHostSupport</span></span>](iwpfhostsupport.md)
