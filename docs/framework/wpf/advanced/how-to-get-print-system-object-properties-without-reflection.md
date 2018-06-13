---
title: 'Cómo: Obtener propiedades de un objeto de sistema de impresión sin reflexión'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- PrintSystemObject [WPF], getting properties
ms.assetid: 43560f28-183d-41c1-b9d1-de7c2552273e
ms.openlocfilehash: 1fa8029b8245aef5e10e9082a1038fd89fc1c84e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544736"
---
# <a name="how-to-get-print-system-object-properties-without-reflection"></a><span data-ttu-id="f802c-102">Cómo: Obtener propiedades de un objeto de sistema de impresión sin reflexión</span><span class="sxs-lookup"><span data-stu-id="f802c-102">How to: Get Print System Object Properties Without Reflection</span></span>
<span data-ttu-id="f802c-103">Use la reflexión para detallar las propiedades (y los tipos de esas propiedades) en un objeto puede ralentizar el rendimiento de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f802c-103">Using reflection to itemize the properties (and the types of those properties) on an object can slow application performance.</span></span> <span data-ttu-id="f802c-104">El <xref:System.Printing.IndexedProperties> espacio de nombres proporciona un medio para obtener esta información sin utilizar la reflexión.</span><span class="sxs-lookup"><span data-stu-id="f802c-104">The <xref:System.Printing.IndexedProperties> namespace provides a means to getting this information with using reflection.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f802c-105">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="f802c-105">Example</span></span>  
 <span data-ttu-id="f802c-106">Los pasos para hacerlo son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="f802c-106">The steps for doing this are as follows.</span></span>  
  
1.  <span data-ttu-id="f802c-107">Cree una instancia del tipo.</span><span class="sxs-lookup"><span data-stu-id="f802c-107">Create an instance of the type.</span></span> <span data-ttu-id="f802c-108">En el ejemplo siguiente, el tipo es el <xref:System.Printing.PrintQueue> tipo que se suministra con Microsoft .NET Framework, pero un código prácticamente idéntico debería funcionar para los tipos que derivan de <xref:System.Printing.PrintSystemObject>.</span><span class="sxs-lookup"><span data-stu-id="f802c-108">In the example below, the type is the <xref:System.Printing.PrintQueue> type that ships with Microsoft .NET Framework, but nearly identical code should work for types that you derive from <xref:System.Printing.PrintSystemObject>.</span></span>  
  
2.  <span data-ttu-id="f802c-109">Crear un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> del tipo <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span><span class="sxs-lookup"><span data-stu-id="f802c-109">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the type's <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A>.</span></span> <span data-ttu-id="f802c-110">El <xref:System.Collections.DictionaryEntry.Value%2A> propiedad de cada entrada de este diccionario es un objeto de uno de los tipos derivados de <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="f802c-110">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span>  
  
3.  <span data-ttu-id="f802c-111">Enumerar a los miembros del diccionario.</span><span class="sxs-lookup"><span data-stu-id="f802c-111">Enumerate the members of the dictionary.</span></span> <span data-ttu-id="f802c-112">Para cada uno de ellos, haga lo siguiente.</span><span class="sxs-lookup"><span data-stu-id="f802c-112">For each of them, do the following.</span></span>  
  
4.  <span data-ttu-id="f802c-113">Convierta el valor de cada entrada para <xref:System.Printing.IndexedProperties.PrintProperty> y usarlo para crear un <xref:System.Printing.IndexedProperties.PrintProperty> objeto.</span><span class="sxs-lookup"><span data-stu-id="f802c-113">Up-cast the value of each entry to <xref:System.Printing.IndexedProperties.PrintProperty> and use it to create a <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
5.  <span data-ttu-id="f802c-114">Obtiene el tipo de la <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> de cada uno de los <xref:System.Printing.IndexedProperties.PrintProperty> objeto.</span><span class="sxs-lookup"><span data-stu-id="f802c-114">Get the type of the <xref:System.Printing.IndexedProperties.PrintProperty.Value%2A> of each of the <xref:System.Printing.IndexedProperties.PrintProperty> object.</span></span>  
  
 [!code-csharp[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/csharp/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/CSharp/Program.cs#showpropertytypeswithoutreflection)]
 [!code-vb[GetPrintObjectPropertyTypesWithoutReflection#ShowPropertyTypesWithoutReflection](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/GetPrintObjectPropertyTypesWithoutReflection/visualbasic/program.vb#showpropertytypeswithoutreflection)]  
  
## <a name="see-also"></a><span data-ttu-id="f802c-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="f802c-115">See Also</span></span>  
 <xref:System.Printing.IndexedProperties.PrintProperty>  
 <xref:System.Printing.PrintSystemObject>  
 <xref:System.Printing.IndexedProperties>  
 <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>  
 <xref:System.Printing.LocalPrintServer>  
 <xref:System.Printing.PrintQueue>  
 <xref:System.Collections.DictionaryEntry>  
 [<span data-ttu-id="f802c-116">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="f802c-116">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="f802c-117">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="f802c-117">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)
