---
ms.openlocfilehash: 4ad7c4c2781480c08ad4cf27e40de445b1c50671
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617301"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="a4763-101">El constructor EncoderParameter está obsoleto</span><span class="sxs-lookup"><span data-stu-id="a4763-101">EncoderParameter ctor is obsolete</span></span>

#### <a name="details"></a><span data-ttu-id="a4763-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="a4763-102">Details</span></span>

<span data-ttu-id="a4763-103">El constructor <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> está obsoleto e introducirá advertencias de compilación si se usa.</span><span class="sxs-lookup"><span data-stu-id="a4763-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="a4763-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="a4763-104">Suggestion</span></span>

<span data-ttu-id="a4763-105">Aunque el constructor <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> seguirá funcionando, en su lugar se debe usar el constructor siguiente para evitar la advertencia de compilación obsoleta al volver a compilar el código con las herramientas de .NET Framework 4.5: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="a4763-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>

| <span data-ttu-id="a4763-106">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="a4763-106">Name</span></span>    | <span data-ttu-id="a4763-107">Valor</span><span class="sxs-lookup"><span data-stu-id="a4763-107">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="a4763-108">Ámbito</span><span class="sxs-lookup"><span data-stu-id="a4763-108">Scope</span></span>   | <span data-ttu-id="a4763-109">Secundaria</span><span class="sxs-lookup"><span data-stu-id="a4763-109">Minor</span></span>       |
| <span data-ttu-id="a4763-110">Versión</span><span class="sxs-lookup"><span data-stu-id="a4763-110">Version</span></span> | <span data-ttu-id="a4763-111">4.5</span><span class="sxs-lookup"><span data-stu-id="a4763-111">4.5</span></span>         |
| <span data-ttu-id="a4763-112">Tipo</span><span class="sxs-lookup"><span data-stu-id="a4763-112">Type</span></span>    | <span data-ttu-id="a4763-113">Redestinación</span><span class="sxs-lookup"><span data-stu-id="a4763-113">Retargeting</span></span> |

#### <a name="affected-apis"></a><span data-ttu-id="a4763-114">API afectadas</span><span class="sxs-lookup"><span data-stu-id="a4763-114">Affected APIs</span></span>

- <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>
