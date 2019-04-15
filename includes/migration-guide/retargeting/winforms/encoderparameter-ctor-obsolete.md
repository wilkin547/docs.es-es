---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234801"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="bf374-101">El constructor EncoderParameter está obsoleto</span><span class="sxs-lookup"><span data-stu-id="bf374-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="bf374-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="bf374-102">Details</span></span>|<span data-ttu-id="bf374-103">El constructor <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> está obsoleto e introducirá advertencias de compilación si se usa.</span><span class="sxs-lookup"><span data-stu-id="bf374-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="bf374-104">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="bf374-104">Suggestion</span></span>|<span data-ttu-id="bf374-105">Aunque el constructor <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> seguirá funcionando, en su lugar se debe usar el constructor siguiente para evitar la advertencia de compilación obsoleta al volver a compilar el código con las herramientas de .NET Framework 4.5: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="bf374-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="bf374-106">Ámbito</span><span class="sxs-lookup"><span data-stu-id="bf374-106">Scope</span></span>|<span data-ttu-id="bf374-107">Secundaria</span><span class="sxs-lookup"><span data-stu-id="bf374-107">Minor</span></span>|
|<span data-ttu-id="bf374-108">Versión</span><span class="sxs-lookup"><span data-stu-id="bf374-108">Version</span></span>|<span data-ttu-id="bf374-109">4.5</span><span class="sxs-lookup"><span data-stu-id="bf374-109">4.5</span></span>|
|<span data-ttu-id="bf374-110">Tipo</span><span class="sxs-lookup"><span data-stu-id="bf374-110">Type</span></span>|<span data-ttu-id="bf374-111">Redestinación</span><span class="sxs-lookup"><span data-stu-id="bf374-111">Retargeting</span></span>|
|<span data-ttu-id="bf374-112">API afectadas</span><span class="sxs-lookup"><span data-stu-id="bf374-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
