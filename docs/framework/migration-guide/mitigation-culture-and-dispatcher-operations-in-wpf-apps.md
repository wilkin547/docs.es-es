---
title: "Mitigación: Referencia cultural y operaciones de distribuidor en aplicaciones WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 455c1452-8ce0-45ae-a092-21fb8edf1cac
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 41fc52679884d547809f1c1e9f47e29eb668cb8e
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-culture-and-dispatcher-operations-in-wpf-apps"></a><span data-ttu-id="a3ec8-102">Mitigación: Referencia cultural y operaciones de distribuidor en aplicaciones WPF</span><span class="sxs-lookup"><span data-stu-id="a3ec8-102">Mitigation: Culture and Dispatcher Operations in WPF Apps</span></span>
<span data-ttu-id="a3ec8-103">En las aplicaciones destinadas a .NET Framework 4.6 y .NET Framework 4.6.1, los cambios de las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> realizados en <xref:System.Windows.Threading.Dispatcher> se pierden al final de dicha operación de distribuidor.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-103">In apps that target the .NET Framework 4.6 and the .NET Framework 4.6.1, changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties that are made within a <xref:System.Windows.Threading.Dispatcher> are lost at the end of that dispatcher operation.</span></span> <span data-ttu-id="a3ec8-104">De igual modo, los cambios efectuados en <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> fuera de una operación de distribuidor pueden no reflejarse cuando se ejecute dicha operación.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-104">Similarly, changes to <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> made outside of a dispatcher operation may not be reflected when that operation executes.</span></span>  
  
 <span data-ttu-id="a3ec8-105">Esto se debe a que un cambio de <xref:System.Threading.ExecutionContext> da lugar a que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> se almacenen en el contexto de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-105">This is due to a change in <xref:System.Threading.ExecutionContext> that causes the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> to be stored in the execution context.</span></span> <span data-ttu-id="a3ec8-106">Las operaciones de distribuidor de WPF almacenan el contexto de ejecución usado para iniciar la operación y restaurar el contexto anterior cuando la operación se complete.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-106">WPF dispatcher operations store the execution context used to begin the operation and restore the previous context when the operation is completed.</span></span> <span data-ttu-id="a3ec8-107">Dado que <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> ahora forman parte de este contexto, los cambios efectuados en ellas como parte de una operación de distribuidor no persisten fuera de la operación.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-107">Because <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> are now part of that context, changes to them within a dispatcher operation are not persisted outside of the operation.</span></span>  
  
## <a name="impact"></a><span data-ttu-id="a3ec8-108">Impacto</span><span class="sxs-lookup"><span data-stu-id="a3ec8-108">Impact</span></span>  
 <span data-ttu-id="a3ec8-109">En términos prácticos, significa que los cambios efectuados en las propiedades <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> y <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> pueden no transmitirse entre devoluciones de llamadas de la IU de WPF y otro código de alguna aplicación WPF.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-109">Practically, this means that changes to the <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> and  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> properties may not flow between WPF UI callbacks and other code in a WPF application.</span></span>  
  
## <a name="mitigation"></a><span data-ttu-id="a3ec8-110">Mitigación</span><span class="sxs-lookup"><span data-stu-id="a3ec8-110">Mitigation</span></span>  
 <span data-ttu-id="a3ec8-111">Las aplicaciones afectadas por este cambio pueden encontrar una solución alternativa a este problema de dos formas:</span><span class="sxs-lookup"><span data-stu-id="a3ec8-111">Apps affected by this change may work around it in either of two ways:</span></span>  
  
-   <span data-ttu-id="a3ec8-112">Al almacenar los objetos <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> deseados y comprobar todos los cuerpos de la operación <xref:System.Windows.Threading.Dispatcher> (incluidos los controladores de devolución de llamadas de eventos de UI) en que los objetos <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> o <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> correctos están establecidos.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-112">By storing the desired <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> in a field and checking in all <xref:System.Windows.Threading.Dispatcher> operation bodies (including UI event callback handlers) that the correct <xref:System.Globalization.CultureInfo.CurrentCulture%2A?displayProperty=fullName> or  <xref:System.Globalization.CultureInfo.CurrentUICulture%2A?displayProperty=fullName> is set.</span></span>  
  
-   <span data-ttu-id="a3ec8-113">Como el cambio en <xref:System.Threading.ExecutionContext> solo afecta a las aplicaciones WPF destinadas a .NET Framework 4.6 o .NET Framework 4.6.1, podría evitarse con .NET Framework 4.5.2 o a partir de la versión .NET Framework 4.6.2.</span><span class="sxs-lookup"><span data-stu-id="a3ec8-113">Because the change to <xref:System.Threading.ExecutionContext> only affects WPF apps that target the .NET Framework 4.6 or the .NET Framework 4.6.1, this change can be avoided by targeting the .NET Framework 4.5.2 or by targeting a version of the .NET Framework starting with 4.6.2.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3ec8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3ec8-114">See Also</span></span>  
 [<span data-ttu-id="a3ec8-115">Cambios de redestinación</span><span class="sxs-lookup"><span data-stu-id="a3ec8-115">Retargeting Changes</span></span>](../../../docs/framework/migration-guide/retargeting-changes-in-the-net-framework-4-6.md)

