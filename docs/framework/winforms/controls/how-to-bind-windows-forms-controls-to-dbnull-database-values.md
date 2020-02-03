---
title: Enlazar controles a valores de base de datos DBNull
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BindingSource component [Windows Forms], binding to DBNull values
- examples [Windows Forms], BindingSource component
- controls [Windows Forms], binding to DBNull values
ms.assetid: 96494e6f-5f40-4f83-af97-bbd7192c2af8
ms.openlocfilehash: 175d7f5aee2540916480e2c55a485af1f9d16653
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746666"
---
# <a name="how-to-bind-windows-forms-controls-to-dbnull-database-values"></a><span data-ttu-id="acd96-102">Cómo: Enlazar controles de formularios Windows Forms a valores de base de datos DBNull</span><span class="sxs-lookup"><span data-stu-id="acd96-102">How to: Bind Windows Forms Controls to DBNull Database Values</span></span>
<span data-ttu-id="acd96-103">Cuando enlaza los controles de Windows Forms a un origen de datos y ese origen devuelve un valor <xref:System.DBNull>, puede sustituir un valor adecuado sin controlar, dar formato o analizar eventos.</span><span class="sxs-lookup"><span data-stu-id="acd96-103">When you bind Windows Forms controls to a data source and the data source returns a <xref:System.DBNull> value, you can substitute an appropriate value without handling, formatting, or parsing events.</span></span> <span data-ttu-id="acd96-104">La propiedad <xref:System.Windows.Forms.Binding.NullValue%2A> convertirá <xref:System.DBNull> en un objeto especificado al dar formato o analizar los valores de origen de datos.</span><span class="sxs-lookup"><span data-stu-id="acd96-104">The <xref:System.Windows.Forms.Binding.NullValue%2A> property will convert <xref:System.DBNull> to a specified object when formatting or parsing the data source values.</span></span>  
  
## <a name="example"></a><span data-ttu-id="acd96-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="acd96-105">Example</span></span>  
 <span data-ttu-id="acd96-106">El ejemplo siguiente muestra cómo enlazar un valor <xref:System.DBNull> en dos situaciones diferentes.</span><span class="sxs-lookup"><span data-stu-id="acd96-106">The following example demonstrates how to bind a <xref:System.DBNull> value in two different situations.</span></span> <span data-ttu-id="acd96-107">En la primera se muestra cómo establecer <xref:System.Windows.Forms.Binding.NullValue%2A> para una propiedad de cadena y la segunda muestra cómo establecer <xref:System.Windows.Forms.Binding.NullValue%2A> para una propiedad de imagen.</span><span class="sxs-lookup"><span data-stu-id="acd96-107">The first demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for a string property; the second demonstrates how to set the <xref:System.Windows.Forms.Binding.NullValue%2A> for an image property.</span></span>  
  
 [!code-csharp[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/CS/form1.cs#1)]
 [!code-vb[System.Windows.Forms.BindingDBNull#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.BindingDBNull/VB/form1.vb#1)]  
  
 <span data-ttu-id="acd96-108">Los tipos de la propiedad enlazada y la propiedad <xref:System.Windows.Forms.Binding.NullValue%2A> debe ser iguales. De lo contrario, se producirá un error y no se procesará ningún valor <xref:System.Windows.Forms.Binding.NullValue%2A>.</span><span class="sxs-lookup"><span data-stu-id="acd96-108">The types of the bound property and the <xref:System.Windows.Forms.Binding.NullValue%2A> property must be the same or an error will result, and no further <xref:System.Windows.Forms.Binding.NullValue%2A> values will be processed.</span></span> <span data-ttu-id="acd96-109">En esta situación, no tendrá lugar ninguna excepción.</span><span class="sxs-lookup"><span data-stu-id="acd96-109">In this situation, an exception will not be thrown.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="acd96-110">Compilar el código</span><span class="sxs-lookup"><span data-stu-id="acd96-110">Compiling the Code</span></span>  
 <span data-ttu-id="acd96-111">Para este ejemplo se necesita:</span><span class="sxs-lookup"><span data-stu-id="acd96-111">This example requires:</span></span>  
  
- <span data-ttu-id="acd96-112">Referencias a los ensamblados System, System.Data, System.Drawing y System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="acd96-112">References to the System, System.Data, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="acd96-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="acd96-113">See also</span></span>

- [<span data-ttu-id="acd96-114">Componente BindingSource</span><span class="sxs-lookup"><span data-stu-id="acd96-114">BindingSource Component</span></span>](bindingsource-component.md)
- [<span data-ttu-id="acd96-115">Cómo: Controlar errores y excepciones que se producen con el enlace de datos</span><span class="sxs-lookup"><span data-stu-id="acd96-115">How to: Handle Errors and Exceptions that Occur with Databinding</span></span>](how-to-handle-errors-and-exceptions-that-occur-with-databinding.md)
- [<span data-ttu-id="acd96-116">Cómo: Enlazar un control de Windows Forms a un tipo</span><span class="sxs-lookup"><span data-stu-id="acd96-116">How to: Bind a Windows Forms Control to a Type</span></span>](how-to-bind-a-windows-forms-control-to-a-type.md)
