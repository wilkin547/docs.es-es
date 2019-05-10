---
title: Procedimiento Clonar una impresora
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- print queues [WPF]
- cloning printers [WPF]
- printers [WPF], cloning
- print queues [WPF], cloning
- cloning print queues [WPF]
ms.assetid: dd6997c9-fe04-40f8-88a6-92e3ac0889eb
ms.openlocfilehash: e6af8d6410c4e383990bdaa27f97cc698be71719
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649198"
---
# <a name="how-to-clone-a-printer"></a><span data-ttu-id="7dc5d-102">Procedimiento Clonar una impresora</span><span class="sxs-lookup"><span data-stu-id="7dc5d-102">How to: Clone a Printer</span></span>
<span data-ttu-id="7dc5d-103">En algún momento, la mayoría de las empresas comprará varias impresoras del mismo modelo.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-103">Most businesses will, at some point, buy multiple printers of the same model.</span></span> <span data-ttu-id="7dc5d-104">Normalmente, estas se instalan con valores de configuración prácticamente idénticos.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-104">Typically, these are all installed with virtually identical configuration settings.</span></span> <span data-ttu-id="7dc5d-105">Instalación de cada impresora puede llevar mucho tiempo y propensas a errores.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-105">Installing each printer can be time-consuming and error prone.</span></span> <span data-ttu-id="7dc5d-106">El <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> espacio de nombres y el <xref:System.Printing.PrintServer.InstallPrintQueue%2A> clase que se exponen a través de Microsoft .NET Framework hace posible instalar al instante cualquier número de colas de impresión adicionales que se clonan desde una cola de impresión existente.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-106">The <xref:System.Printing.IndexedProperties?displayProperty=nameWithType> namespace and the <xref:System.Printing.PrintServer.InstallPrintQueue%2A> class that are exposed with Microsoft .NET Framework makes it possible to instantly install any number of additional print queues that are cloned from an existing print queue.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dc5d-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="7dc5d-107">Example</span></span>  
 <span data-ttu-id="7dc5d-108">En el ejemplo siguiente, se clona una segunda cola de impresión desde una cola de impresión existente.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-108">In the example below, a second print queue is cloned from an existing print queue.</span></span> <span data-ttu-id="7dc5d-109">El segundo es distinto del primero solo en su nombre, la ubicación, el puerto y el estado compartido.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-109">The second differs from the first only in its name, location, port, and shared status.</span></span> <span data-ttu-id="7dc5d-110">Los pasos principales para hacerlo son los siguientes.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-110">The major steps for doing this are as follows.</span></span>  
  
1. <span data-ttu-id="7dc5d-111">Crear un <xref:System.Printing.PrintQueue> objetos de impresora existente que se va a clonar.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-111">Create a <xref:System.Printing.PrintQueue> object for the existing printer that is going to be cloned.</span></span>  
  
2. <span data-ttu-id="7dc5d-112">Crear un <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> desde el <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> de la <xref:System.Printing.PrintQueue>.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-112">Create a <xref:System.Printing.IndexedProperties.PrintPropertyDictionary> from the <xref:System.Printing.PrintSystemObject.PropertiesCollection%2A> of the <xref:System.Printing.PrintQueue>.</span></span> <span data-ttu-id="7dc5d-113">El <xref:System.Collections.DictionaryEntry.Value%2A> propiedad de cada entrada de este diccionario es un objeto de uno de los tipos derivados de <xref:System.Printing.IndexedProperties.PrintProperty>.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-113">The <xref:System.Collections.DictionaryEntry.Value%2A> property of each entry in this dictionary is an object of one of the types derived from <xref:System.Printing.IndexedProperties.PrintProperty>.</span></span> <span data-ttu-id="7dc5d-114">Hay dos maneras de establecer el valor de una entrada en este diccionario.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-114">There are two ways to set the value of an entry in this dictionary.</span></span>  
  
    - <span data-ttu-id="7dc5d-115">Usar el diccionario **quitar** y <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> métodos para quitar la entrada y, a continuación, vuelva a agregarlo con el valor deseado.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-115">Use the dictionary's **Remove** and <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.Add%2A> methods to remove the entry and then re-add it with the desired value.</span></span>  
  
    - <span data-ttu-id="7dc5d-116">Usar el diccionario <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> método.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-116">Use the dictionary's <xref:System.Printing.IndexedProperties.PrintPropertyDictionary.SetProperty%2A> method.</span></span>  
  
     <span data-ttu-id="7dc5d-117">El ejemplo siguiente muestra ambas maneras.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-117">The example below illustrates both ways.</span></span>  
  
3. <span data-ttu-id="7dc5d-118">Crear un <xref:System.Printing.IndexedProperties.PrintBooleanProperty> de objeto y establecer su <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> a "IsShared" y su <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> a `true`.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-118">Create a <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "IsShared" and its <xref:System.Printing.IndexedProperties.PrintBooleanProperty.Value%2A> to `true`.</span></span>  
  
4. <span data-ttu-id="7dc5d-119">Use la <xref:System.Printing.IndexedProperties.PrintBooleanProperty> objeto sea el valor de la <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>de entrada "IsShared".</span><span class="sxs-lookup"><span data-stu-id="7dc5d-119">Use the <xref:System.Printing.IndexedProperties.PrintBooleanProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "IsShared" entry.</span></span>  
  
5. <span data-ttu-id="7dc5d-120">Crear un <xref:System.Printing.IndexedProperties.PrintStringProperty> de objeto y establecer su <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> "ShareName" y su <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> un adecuado <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-120">Create a <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "ShareName" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
6. <span data-ttu-id="7dc5d-121">Use la <xref:System.Printing.IndexedProperties.PrintStringProperty> objeto sea el valor de la <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>de entrada "ShareName".</span><span class="sxs-lookup"><span data-stu-id="7dc5d-121">Use the <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "ShareName" entry.</span></span>  
  
7. <span data-ttu-id="7dc5d-122">Crear otro <xref:System.Printing.IndexedProperties.PrintStringProperty> de objeto y establecer su <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> a "Ubicación" y su <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> un adecuado <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-122">Create another <xref:System.Printing.IndexedProperties.PrintStringProperty> object and set its <xref:System.Printing.IndexedProperties.PrintProperty.Name%2A> to "Location" and its <xref:System.Printing.IndexedProperties.PrintStringProperty.Value%2A> to an appropriate <xref:System.String>.</span></span>  
  
8. <span data-ttu-id="7dc5d-123">Use la segunda <xref:System.Printing.IndexedProperties.PrintStringProperty> objeto sea el valor de la <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>de entrada de "Ubicación".</span><span class="sxs-lookup"><span data-stu-id="7dc5d-123">Use the second <xref:System.Printing.IndexedProperties.PrintStringProperty> object to be the value of the <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>'s "Location" entry.</span></span>  
  
9. <span data-ttu-id="7dc5d-124">Crear una matriz de <xref:System.String>s.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-124">Create an array of <xref:System.String>s.</span></span> <span data-ttu-id="7dc5d-125">Cada elemento es el nombre de un puerto en el servidor.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-125">Each item is the name of a port on the server.</span></span>  
  
10. <span data-ttu-id="7dc5d-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> para instalar la nueva impresora con los nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-126">Use <xref:System.Printing.PrintServer.InstallPrintQueue%2A> to install the new printer with the new values.</span></span>  
  
 <span data-ttu-id="7dc5d-127">Es un ejemplo a continuación.</span><span class="sxs-lookup"><span data-stu-id="7dc5d-127">An example is below.</span></span>  
  
 [!code-csharp[ClonePrinter#ClonePrinter](~/samples/snippets/csharp/VS_Snippets_Wpf/ClonePrinter/CSharp/Program.cs#cloneprinter)]
 [!code-vb[ClonePrinter#ClonePrinter](~/samples/snippets/visualbasic/VS_Snippets_Wpf/ClonePrinter/visualbasic/program.vb#cloneprinter)]  
  
## <a name="see-also"></a><span data-ttu-id="7dc5d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dc5d-128">See also</span></span>

- <xref:System.Printing.IndexedProperties>
- <xref:System.Printing.IndexedProperties.PrintPropertyDictionary>
- <xref:System.Printing.LocalPrintServer>
- <xref:System.Printing.PrintQueue>
- <xref:System.Collections.DictionaryEntry>
- [<span data-ttu-id="7dc5d-129">Documentos en WPF</span><span class="sxs-lookup"><span data-stu-id="7dc5d-129">Documents in WPF</span></span>](documents-in-wpf.md)
- [<span data-ttu-id="7dc5d-130">Información general sobre impresión</span><span class="sxs-lookup"><span data-stu-id="7dc5d-130">Printing Overview</span></span>](printing-overview.md)
