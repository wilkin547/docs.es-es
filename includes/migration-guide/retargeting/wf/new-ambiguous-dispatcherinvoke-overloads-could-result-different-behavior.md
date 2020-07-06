---
ms.openlocfilehash: 80e61d4dd5b8d4754a39e95e37475fefff57fcbd
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617263"
---
### <a name="new-ambiguous-dispatcherinvoke-overloads-could-result-in-different-behavior"></a><span data-ttu-id="61da7-101">Las nuevas sobrecargas (ambiguas) de Dispatcher.Invoke pueden generar otro comportamiento</span><span class="sxs-lookup"><span data-stu-id="61da7-101">New (ambiguous) Dispatcher.Invoke overloads could result in different behavior</span></span>

#### <a name="details"></a><span data-ttu-id="61da7-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="61da7-102">Details</span></span>

<span data-ttu-id="61da7-103">.NET Framework 4.5 agrega nuevas sobrecargas para <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType>, entre las que se incluye un parámetro de tipo <xref:System.Action>.</span><span class="sxs-lookup"><span data-stu-id="61da7-103">The .NET Framework 4.5 adds new overloads to <xref:System.Windows.Threading.Dispatcher.Invoke%2A?displayProperty=nameWithType> that include a parameter of type <xref:System.Action>.</span></span> <span data-ttu-id="61da7-104">Cuando el código existente se vuelve a compilar, los compiladores pueden resolver llamadas a métodos Dispatcher.Invoke que tienen un parámetro <xref:System.Delegate> como llamadas a métodos Dispatcher.Invoke con un parámetro <xref:System.Action>.</span><span class="sxs-lookup"><span data-stu-id="61da7-104">When existing code is recompiled, compilers may resolve calls to Dispatcher.Invoke methods that have a <xref:System.Delegate> parameter as calls to Dispatcher.Invoke methods with an <xref:System.Action> parameter.</span></span> <span data-ttu-id="61da7-105">Si una llamada a una sobrecarga de Dispatcher.Invoke con un parámetro <xref:System.Delegate> se resuelve como una llamada a una sobrecarga de Dispatcher.Invoke con un parámetro <xref:System.Action>, se pueden producir las diferencias de comportamiento siguientes:</span><span class="sxs-lookup"><span data-stu-id="61da7-105">If a call to a Dispatcher.Invoke overload with a  <xref:System.Delegate> parameter is resolved as a call to a Dispatcher.Invoke overload with an <xref:System.Action> parameter, the following differences in behavior may occur:</span></span>

- <span data-ttu-id="61da7-106">Si se produce una excepción, no se inician los eventos <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> y <xref:System.Windows.Threading.Dispatcher.UnhandledException>.</span><span class="sxs-lookup"><span data-stu-id="61da7-106">If an exception occurs, the <xref:System.Windows.Threading.Dispatcher.UnhandledExceptionFilter> and <xref:System.Windows.Threading.Dispatcher.UnhandledException> events are not raised.</span></span> <span data-ttu-id="61da7-107">En su lugar, las excepciones se controlan mediante el evento <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="61da7-107">Instead, exceptions are handled by the <xref:System.Threading.Tasks.TaskScheduler.UnobservedTaskException?displayProperty=fullName> event.</span></span>
- <span data-ttu-id="61da7-108">Las llamadas a algunos miembros, como <xref:System.Windows.Threading.DispatcherOperation.Result>, se bloquean hasta que se completa la operación.</span><span class="sxs-lookup"><span data-stu-id="61da7-108">Calls to some members, such as <xref:System.Windows.Threading.DispatcherOperation.Result>, block until the operation has completed.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="61da7-109">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="61da7-109">Suggestion</span></span>

<span data-ttu-id="61da7-110">Para evitar ambigüedades (y posibles diferencias en el control de excepciones o los comportamientos de bloqueo), el código que llame a Dispatcher.Invoke puede pasar un objeto vacío [] como segundo parámetro de la llamada a Invoke para garantizar que la resolución se resuelva en la sobrecarga del método de .NET Framework 4.0.</span><span class="sxs-lookup"><span data-stu-id="61da7-110">To avoid ambiguity (and potential differences in exception handling or blocking behaviors), code calling Dispatcher.Invoke can pass an empty object[] as a second parameter to the Invoke call to be sure of resolving to the .NET Framework 4.0 method overload.</span></span>

| <span data-ttu-id="61da7-111">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="61da7-111">Name</span></span>    | <span data-ttu-id="61da7-112">Valor</span><span class="sxs-lookup"><span data-stu-id="61da7-112">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="61da7-113">Ámbito</span><span class="sxs-lookup"><span data-stu-id="61da7-113">Scope</span></span>   | <span data-ttu-id="61da7-114">Secundaria</span><span class="sxs-lookup"><span data-stu-id="61da7-114">Minor</span></span>       |
| <span data-ttu-id="61da7-115">Versión</span><span class="sxs-lookup"><span data-stu-id="61da7-115">Version</span></span> | <span data-ttu-id="61da7-116">4.5</span><span class="sxs-lookup"><span data-stu-id="61da7-116">4.5</span></span>         |
| <span data-ttu-id="61da7-117">Tipo</span><span class="sxs-lookup"><span data-stu-id="61da7-117">Type</span></span>    | <span data-ttu-id="61da7-118">Redestinación</span><span class="sxs-lookup"><span data-stu-id="61da7-118">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="61da7-119">API afectadas</span><span class="sxs-lookup"><span data-stu-id="61da7-119">Affected APIs</span></span>

- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.TimeSpan,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
- <xref:System.Windows.Threading.Dispatcher.Invoke(System.Delegate,System.Windows.Threading.DispatcherPriority,System.Object[])?displayProperty=nameWithType>
