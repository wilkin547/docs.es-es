---
title: Manipulaciones de cadena básicas en .NET
description: Vea un ejemplo que llama a muchos métodos de cadena.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- strings [.NET], examples
ms.assetid: 121d1eae-251b-44c0-8818-57da04b8215e
ms.openlocfilehash: cc04f0c874b732668b4813f8325bd7060927f22a
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889132"
---
# <a name="how-to-perform-basic-string-manipulations-in-net"></a><span data-ttu-id="22958-103">Procedimiento para realizar manipulaciones de cadena básicas en .NET</span><span class="sxs-lookup"><span data-stu-id="22958-103">How to: Perform Basic String Manipulations in .NET</span></span>

<span data-ttu-id="22958-104">En el ejemplo siguiente, se usan algunos de los métodos descritos en los temas de [Operaciones básicas de cadenas](basic-string-operations.md) para construir una clase que realice manipulaciones de cadena de una manera que podría encontrarse en una aplicación real.</span><span class="sxs-lookup"><span data-stu-id="22958-104">The following example uses some of the methods discussed in the [Basic String Operations](basic-string-operations.md) topics to construct a class that performs string manipulations in a manner that might be found in a real-world application.</span></span> <span data-ttu-id="22958-105">La clase `MailToData` almacena el nombre y dirección de los individuos en propiedades distintas y proporciona una forma de combinar los campos `City`, `State` y `Zip` en una única cadena para mostrar al usuario.</span><span class="sxs-lookup"><span data-stu-id="22958-105">The `MailToData` class stores the name and address of an individual in separate properties and provides a way to combine the `City`, `State`, and `Zip` fields into a single string for display to the user.</span></span> <span data-ttu-id="22958-106">Además, la clase permite al usuario que escriba la información sobre la ciudad, estado y código postal como una sola cadena; de forma automática, la aplicación analiza la cadena única y escribe la información adecuada en la propiedad correspondiente.</span><span class="sxs-lookup"><span data-stu-id="22958-106">Furthermore, the class allows the user to enter the city, state, and ZIP Code information as a single string; the application automatically parses the single string and enters the proper information into the corresponding property.</span></span>  
  
<span data-ttu-id="22958-107">Para simplificar, en este ejemplo se usa una aplicación de consola con una interfaz de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="22958-107">For simplicity, this example uses a console application with a command-line interface.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22958-108">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="22958-108">Example</span></span>  

[!code-csharp[Conceptual.String.BasicOps#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.string.basicops/cs/basicops.cs#1)]
[!code-vb[Conceptual.String.BasicOps#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.string.basicops/vb/basicops.vb#1)]  
  
<span data-ttu-id="22958-109">Cuando se ejecuta el código anterior, se pide al usuario que escriba su nombre y dirección.</span><span class="sxs-lookup"><span data-stu-id="22958-109">When the preceding code is executed, the user is asked to enter their name and address.</span></span> <span data-ttu-id="22958-110">La aplicación coloca la información en las propiedades adecuadas y muestra la información al usuario, creando una única cadena que muestra la información sobre la ciudad, el estado y el código postal.</span><span class="sxs-lookup"><span data-stu-id="22958-110">The application places the information in the appropriate properties and displays the information back to the user, creating a single string that displays the city, state, and ZIP Code information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22958-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="22958-111">See also</span></span>

- [<span data-ttu-id="22958-112">Operaciones básicas de cadenas</span><span class="sxs-lookup"><span data-stu-id="22958-112">Basic String Operations</span></span>](basic-string-operations.md)
