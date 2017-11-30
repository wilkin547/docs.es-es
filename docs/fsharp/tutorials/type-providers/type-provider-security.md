---
title: Seguridad del proveedor de tipos
description: "Obtenga información acerca de la seguridad del proveedor de tipo de F #, incluida la forma de cambiar la configuración de confianza de un proveedor de tipos."
keywords: "visual f#, f#, programación funcional"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 9c5a8a1f-5a31-490d-83c0-8beabda75c78
ms.openlocfilehash: c8f03ee90d4dce1d3484a9dfe8951d500d509a2b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="type-provider-security"></a><span data-ttu-id="6b273-104">Seguridad del proveedor de tipos</span><span class="sxs-lookup"><span data-stu-id="6b273-104">Type Provider Security</span></span>

<span data-ttu-id="6b273-105">Proveedores de tipo son ensamblados (archivos DLL) al que hace referencia el proyecto de F # o el script que contienen código para conectarse a orígenes de datos externos y esta información de tipo de superficie para el entorno de tipo de F #.</span><span class="sxs-lookup"><span data-stu-id="6b273-105">Type providers are assemblies (DLLs) referenced by your F# project or script that contain code to connect to external data sources and surface this type information to the F# type environment.</span></span> <span data-ttu-id="6b273-106">Por lo general, solo se ejecuta código en los ensamblados que se hace referencia, al compilar y, a continuación, ejecute el código (o en el caso de una secuencia de comandos, envíe el código de F # Interactive).</span><span class="sxs-lookup"><span data-stu-id="6b273-106">Typically, code in referenced assemblies is only run when you compile and then execute the code (or in the case of a script, send the code to F# Interactive).</span></span> <span data-ttu-id="6b273-107">Sin embargo, un ensamblado de proveedor de tipo se ejecutará dentro de Visual Studio cuando simplemente se explora el código en el editor.</span><span class="sxs-lookup"><span data-stu-id="6b273-107">However, a type provider assembly will run inside Visual Studio when the code is merely browsed in the editor.</span></span> <span data-ttu-id="6b273-108">Esto sucede porque los proveedores de tipo que deba ejecutar para agregar información adicional para el editor, por ejemplo, información rápida sobre herramientas, finalización de IntelliSense y así sucesivamente.</span><span class="sxs-lookup"><span data-stu-id="6b273-108">This happens because type providers need to run to add extra information to the editor, such as Quick Info tooltips, IntelliSense completions, and so on.</span></span> <span data-ttu-id="6b273-109">Como resultado, hay consideraciones de seguridad adicionales para el tipo de proveedor ensamblados, ya que se ejecutan automáticamente en el proceso de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6b273-109">As a result, there are extra security considerations for type provider assemblies, since they run automatically inside the Visual Studio process.</span></span>


## <a name="security-warning-dialog"></a><span data-ttu-id="6b273-110">Cuadro de diálogo de advertencia de seguridad</span><span class="sxs-lookup"><span data-stu-id="6b273-110">Security Warning Dialog</span></span>
<span data-ttu-id="6b273-111">Cuando se usa un ensamblado de proveedor de tipo concreto por primera vez, Visual Studio muestra un cuadro de diálogo de seguridad que le advierte que el proveedor de tipo está a punto de ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="6b273-111">When using a particular type provider assembly for the first time, Visual Studio displays a security dialog that warns you that the type provider is about to run.</span></span> <span data-ttu-id="6b273-112">Antes de Visual Studio carga el proveedor de tipos, ofrece la oportunidad de decidir si confiar en este proveedor determinado.</span><span class="sxs-lookup"><span data-stu-id="6b273-112">Before Visual Studio loads the type provider, it gives you the opportunity to decide if you trust this particular provider.</span></span> <span data-ttu-id="6b273-113">Si confía en el origen del proveedor de tipo, a continuación, seleccione "confiar en este proveedor de tipo".</span><span class="sxs-lookup"><span data-stu-id="6b273-113">If you trust the source of the type provider, then select "I trust this type provider."</span></span> <span data-ttu-id="6b273-114">Si no confía en el origen del proveedor de tipo, a continuación, seleccione "no confiar en este proveedor de tipo."</span><span class="sxs-lookup"><span data-stu-id="6b273-114">If you do not trust the source of the type provider, then select "I do not trust this type provider."</span></span> <span data-ttu-id="6b273-115">Confiar en el proveedor permite que se ejecuta dentro de Visual Studio y proporcionar IntelliSense y compilar características.</span><span class="sxs-lookup"><span data-stu-id="6b273-115">Trusting the provider enables it to run inside Visual Studio and provide IntelliSense and build features.</span></span> <span data-ttu-id="6b273-116">Pero si el propio proveedor de tipo es malintencionado, al ejecutar su código pueda poner en peligro el equipo.</span><span class="sxs-lookup"><span data-stu-id="6b273-116">But if the type provider itself is malicious, running its code could compromise your machine.</span></span>

<span data-ttu-id="6b273-117">Si el proyecto contiene código que hace referencia a proveedores de tipos que eligió en el cuadro de diálogo no confía, a continuación, en tiempo de compilación, el compilador notificará un error que indica que el proveedor de tipos no es de confianza.</span><span class="sxs-lookup"><span data-stu-id="6b273-117">If your project contains code that references type providers that you chose in the dialog not to trust, then at compile time, the compiler will report an error that indicates that the type provider is untrusted.</span></span> <span data-ttu-id="6b273-118">Los tipos que son depende del proveedor de tipo no es de confianza se indican mediante un subrayado ondulado rojo.</span><span class="sxs-lookup"><span data-stu-id="6b273-118">Any types that are dependent on the untrusted type provider are indicated by red squiggles.</span></span> <span data-ttu-id="6b273-119">Es seguro examinar el código en el editor.</span><span class="sxs-lookup"><span data-stu-id="6b273-119">It is safe to browse the code in the editor.</span></span>

<span data-ttu-id="6b273-120">Si decide cambiar la configuración de confianza directamente en Visual Studio, realice los pasos siguientes.</span><span class="sxs-lookup"><span data-stu-id="6b273-120">If you decide to change the trust setting directly in Visual Studio, perform the following steps.</span></span>


#### <a name="to-change-the-trust-settings-for-type-providers"></a><span data-ttu-id="6b273-121">Para cambiar la configuración de confianza para los proveedores de tipo</span><span class="sxs-lookup"><span data-stu-id="6b273-121">To change the trust settings for type providers</span></span>

1. <span data-ttu-id="6b273-122">En el `Tools` menú, seleccione `Options`y expanda el `F# Tools` nodo.</span><span class="sxs-lookup"><span data-stu-id="6b273-122">On the `Tools` menu, select `Options`, and expand the `F# Tools` node.</span></span>
<br />

2. <span data-ttu-id="6b273-123">Seleccione `Type Providers`, en la lista de proveedores de tipo, seleccione la casilla de verificación para los proveedores de tipo confía y desactive la casilla de verificación para los que no confías.</span><span class="sxs-lookup"><span data-stu-id="6b273-123">Select `Type Providers`, and in the list of type providers, select the check box for type providers you trust, and clear the check box for those you don't trust.</span></span>
<br />


## <a name="see-also"></a><span data-ttu-id="6b273-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b273-124">See Also</span></span>
[<span data-ttu-id="6b273-125">Proveedores de tipos</span><span class="sxs-lookup"><span data-stu-id="6b273-125">Type Providers</span></span>](index.md)
