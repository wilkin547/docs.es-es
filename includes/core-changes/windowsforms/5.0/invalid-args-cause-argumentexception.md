---
ms.openlocfilehash: 5212c5d9513a8ef5f51693857d0ddb60db4e49b9
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158413"
---
### <a name="winforms-methods-now-throw-argumentexception"></a><span data-ttu-id="ad8c9-101">Los métodos de WinForms inician ahora la excepción ArgumentException</span><span class="sxs-lookup"><span data-stu-id="ad8c9-101">WinForms methods now throw ArgumentException</span></span>

<span data-ttu-id="ad8c9-102">Algunos métodos de Windows Forms inician ahora una excepción <xref:System.ArgumentException> en los argumentos no válidos, donde antes no lo hacían.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-102">Some Windows Forms methods now throw an <xref:System.ArgumentException> for invalid arguments, where previously they did not.</span></span>

#### <a name="change-description"></a><span data-ttu-id="ad8c9-103">Descripción del cambio</span><span class="sxs-lookup"><span data-stu-id="ad8c9-103">Change description</span></span>

<span data-ttu-id="ad8c9-104">Anteriormente, al pasar argumentos de un tipo inesperado o incorrecto a ciertos métodos de Windows Forms se originaba un estado indeterminado.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-104">Previously, passing arguments of an unexpected or incorrect type to certain Windows Forms methods would result in an indeterminate state.</span></span> <span data-ttu-id="ad8c9-105">A partir de .NET 5.0, estos métodos inician una excepción <xref:System.ArgumentException> cuando se pasan argumentos no válidos.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-105">Starting in .NET 5.0, these methods now throw an <xref:System.ArgumentException> when passed invalid arguments.</span></span>

<span data-ttu-id="ad8c9-106">El inicio de una <xref:System.ArgumentException> se ajusta al comportamiento del tiempo de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-106">Throwing an <xref:System.ArgumentException> conforms to the behavior of the .NET runtime.</span></span> <span data-ttu-id="ad8c9-107">También mejora la experiencia de depuración al comunicar claramente qué argumento no es válido.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-107">It also improves the debugging experience by clearly communicating which argument is invalid.</span></span>

<span data-ttu-id="ad8c9-108">En la tabla siguiente se enumeran los métodos y parámetros afectados:</span><span class="sxs-lookup"><span data-stu-id="ad8c9-108">The following table lists the affected methods and parameters:</span></span>

| <span data-ttu-id="ad8c9-109">Método</span><span class="sxs-lookup"><span data-stu-id="ad8c9-109">Method</span></span> | <span data-ttu-id="ad8c9-110">Nombre de parámetro</span><span class="sxs-lookup"><span data-stu-id="ad8c9-110">Parameter name</span></span> | <span data-ttu-id="ad8c9-111">Condición</span><span class="sxs-lookup"><span data-stu-id="ad8c9-111">Condition</span></span> | <span data-ttu-id="ad8c9-112">Versión agregada</span><span class="sxs-lookup"><span data-stu-id="ad8c9-112">Version added</span></span> |
|-|-|-|
| <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName> | `item` | <span data-ttu-id="ad8c9-113">El argumento no es del tipo <xref:System.Windows.Forms.TabPage>.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-113">Argument is not of type <xref:System.Windows.Forms.TabPage>.</span></span> | <span data-ttu-id="ad8c9-114">5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="ad8c9-114">5.0 Preview 1</span></span> |

#### <a name="version-introduced"></a><span data-ttu-id="ad8c9-115">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="ad8c9-115">Version introduced</span></span>

<span data-ttu-id="ad8c9-116">.NET 5.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="ad8c9-116">.NET 5.0 Preview 1</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="ad8c9-117">Acción recomendada</span><span class="sxs-lookup"><span data-stu-id="ad8c9-117">Recommended action</span></span>

- <span data-ttu-id="ad8c9-118">Actualice el código para evitar pasar argumentos no válidos.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-118">Update the code to prevent passing invalid arguments.</span></span>
- <span data-ttu-id="ad8c9-119">Si es necesario, controle una excepción <xref:System.ArgumentException> al llamar al método.</span><span class="sxs-lookup"><span data-stu-id="ad8c9-119">If necessary, handle an <xref:System.ArgumentException> when calling the method.</span></span>

#### <a name="category"></a><span data-ttu-id="ad8c9-120">Categoría</span><span class="sxs-lookup"><span data-stu-id="ad8c9-120">Category</span></span>

<span data-ttu-id="ad8c9-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="ad8c9-121">Windows Forms</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="ad8c9-122">API afectadas</span><span class="sxs-lookup"><span data-stu-id="ad8c9-122">Affected APIs</span></span>

- <xref:System.Windows.Forms.TabControl.GetToolTipText(System.Object)?displayProperty=fullName>

<!-- 

### Affected APIs

- `M:System.Windows.Forms.TabControl.GetToolTipText(System.Object)`

-->
