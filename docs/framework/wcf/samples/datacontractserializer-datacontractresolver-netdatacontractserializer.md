---
description: 'Más información sobre: usar DataContractSerializer y DataContractResolver para proporcionar la funcionalidad de NetDataContractSerializer'
title: Utilizar DataContractSerializer y DataContractResolver para proporcionar la funcionalidad de NetDataContractSerializer
ms.date: 03/30/2017
ms.assetid: 1376658f-f695-45f7-a7e0-94664e9619ff
ms.openlocfilehash: 40a6a0b939439ecc246caabfd5b28e78e006aa72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99755816"
---
# <a name="using-datacontractserializer-and-datacontractresolver-to-provide-the-functionality-of-netdatacontractserializer"></a><span data-ttu-id="10a75-103">Utilizar DataContractSerializer y DataContractResolver para proporcionar la funcionalidad de NetDataContractSerializer</span><span class="sxs-lookup"><span data-stu-id="10a75-103">Using DataContractSerializer and DataContractResolver to Provide the Functionality of NetDataContractSerializer</span></span>

<span data-ttu-id="10a75-104">En este ejemplo se muestra el modo en que el uso de un <xref:System.Runtime.Serialization.DataContractSerializer> con un <xref:System.Runtime.Serialization.DataContractResolver> adecuado proporciona la misma funcionalidad que <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="10a75-104">This sample demonstrates how the use of <xref:System.Runtime.Serialization.DataContractSerializer> with an appropriate <xref:System.Runtime.Serialization.DataContractResolver> provides the same functionality as <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="10a75-105">En este ejemplo se muestra cómo crear el <xref:System.Runtime.Serialization.DataContractResolver> adecuado y cómo agregarlo a <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="10a75-105">This sample shows how to create the appropriate <xref:System.Runtime.Serialization.DataContractResolver> and how to add it to the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span>

## <a name="sample-details"></a><span data-ttu-id="10a75-106">Detalles del ejemplo</span><span class="sxs-lookup"><span data-stu-id="10a75-106">Sample details</span></span>

 <span data-ttu-id="10a75-107"><xref:System.Runtime.Serialization.NetDataContractSerializer> difiere de <xref:System.Runtime.Serialization.DataContractSerializer> en un aspecto importante: <xref:System.Runtime.Serialization.NetDataContractSerializer> incluye información de tipos CLR en el XML serializado, mientras que <xref:System.Runtime.Serialization.DataContractSerializer> no.</span><span class="sxs-lookup"><span data-stu-id="10a75-107"><xref:System.Runtime.Serialization.NetDataContractSerializer> differs from <xref:System.Runtime.Serialization.DataContractSerializer> in one important way: <xref:System.Runtime.Serialization.NetDataContractSerializer> includes CLR type information in the serialized XML, whereas <xref:System.Runtime.Serialization.DataContractSerializer> does not.</span></span> <span data-ttu-id="10a75-108">Por lo tanto, solo se puede utilizar <xref:System.Runtime.Serialization.NetDataContractSerializer> si ambos extremos, los de la serialización y los de la deserialización, comparten los mismos tipos de CLR.</span><span class="sxs-lookup"><span data-stu-id="10a75-108">Therefore, <xref:System.Runtime.Serialization.NetDataContractSerializer> can be used only if both the serializing and deserializing ends share the same CLR types.</span></span> <span data-ttu-id="10a75-109">Sin embargo, se recomienda utilizar <xref:System.Runtime.Serialization.DataContractSerializer> porque su rendimiento es mejor que el de <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="10a75-109">However, it is recommended to use <xref:System.Runtime.Serialization.DataContractSerializer> because its performance is better than <xref:System.Runtime.Serialization.NetDataContractSerializer>.</span></span> <span data-ttu-id="10a75-110">Puede cambiar la información que se serializa en <xref:System.Runtime.Serialization.DataContractSerializer> agregando un <xref:System.Runtime.Serialization.DataContractResolver> a él.</span><span class="sxs-lookup"><span data-stu-id="10a75-110">You can change the information that is serialized in <xref:System.Runtime.Serialization.DataContractSerializer> by adding a <xref:System.Runtime.Serialization.DataContractResolver> to it.</span></span>

 <span data-ttu-id="10a75-111">Este ejemplo consta de dos proyectos.</span><span class="sxs-lookup"><span data-stu-id="10a75-111">This sample consists of two projects.</span></span> <span data-ttu-id="10a75-112">El primer proyecto utiliza <xref:System.Runtime.Serialization.NetDataContractSerializer> para serializar un objeto.</span><span class="sxs-lookup"><span data-stu-id="10a75-112">The first project uses <xref:System.Runtime.Serialization.NetDataContractSerializer> to serialize an object.</span></span> <span data-ttu-id="10a75-113">El segundo proyecto utiliza <xref:System.Runtime.Serialization.DataContractSerializer> con <xref:System.Runtime.Serialization.DataContractResolver> para proporcionar la misma funcionalidad que el primer proyecto.</span><span class="sxs-lookup"><span data-stu-id="10a75-113">The second project uses <xref:System.Runtime.Serialization.DataContractSerializer> with a <xref:System.Runtime.Serialization.DataContractResolver> to provide the same functionality as the first project.</span></span>

 <span data-ttu-id="10a75-114">El siguiente ejemplo de código muestra la implementación de un <xref:System.Runtime.Serialization.DataContractResolver> personalizado denominado `MyDataContractResolver` que se agrega a <xref:System.Runtime.Serialization.DataContractSerializer> en el proyecto DCSwithDCR.</span><span class="sxs-lookup"><span data-stu-id="10a75-114">The following code example shows the implementation of a custom <xref:System.Runtime.Serialization.DataContractResolver> named `MyDataContractResolver` that is added to the <xref:System.Runtime.Serialization.DataContractSerializer> in the DCSwithDCR project.</span></span>

```csharp
class MyDataContractResolver : DataContractResolver
{
    private XmlDictionary dictionary = new XmlDictionary();

    public MyDataContractResolver()
    {
    }

    // Used at deserialization
    // Allows users to map xsi:type name to any Type
    public override Type ResolveName(string typeName, string typeNamespace, DataContractResolver knownTypeResolver)
    {
        Type type = knownTypeResolver.ResolveName(typeName, typeNamespace, null);
        type ??= Type.GetType(typeName + ", " + typeNamespace);
        return type;
    }

    // Used at serialization
    // Maps any Type to a new xsi:type representation
    public override void ResolveType(Type dataContractType, DataContractResolver knownTypeResolver, out XmlDictionaryString typeName, out XmlDictionaryString typeNamespace)
    {
        knownTypeResolver.ResolveType(dataContractType, null, out typeName, out typeNamespace);
        if (typeName == null || typeNamespace == null)
        {
            XmlDictionary dictionary = new XmlDictionary();
            typeName = dictionary.Add(dataContractType.FullName);
            typeNamespace = dictionary.Add(dataContractType.Assembly.FullName);
        }
    }
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="10a75-115">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="10a75-115">To use this sample</span></span>

1. <span data-ttu-id="10a75-116">Con Visual Studio 2012, abra el archivo de solución Cdrsample. sln.</span><span class="sxs-lookup"><span data-stu-id="10a75-116">Using Visual Studio 2012, open the DCRSample.sln solution file.</span></span>

2. <span data-ttu-id="10a75-117">Haga clic con el botón derecho en el archivo de solución y elija **propiedades**.</span><span class="sxs-lookup"><span data-stu-id="10a75-117">Right-click the solution file and choose **Properties**.</span></span>

3. <span data-ttu-id="10a75-118">En el cuadro de diálogo **páginas de propiedades** de la solución, en **propiedades comunes**, **proyecto de inicio**, seleccione **proyectos de inicio múltiples:**.</span><span class="sxs-lookup"><span data-stu-id="10a75-118">In the **Solution Property Pages** dialog, under **Common Properties**, **Startup Project**, select **Multiple startup projects:**.</span></span>

4. <span data-ttu-id="10a75-119">Junto al proyecto **DCSwithDCR** , seleccione **iniciar** en la lista desplegable **acción** .</span><span class="sxs-lookup"><span data-stu-id="10a75-119">Next to the **DCSwithDCR** project, select **Start** from the **Action** dropdown.</span></span>

5. <span data-ttu-id="10a75-120">Junto al proyecto **NetDCS** , seleccione **iniciar** en la lista desplegable **acción** .</span><span class="sxs-lookup"><span data-stu-id="10a75-120">Next to the **NetDCS** project, select **Start** from the **Action** dropdown.</span></span>

6. <span data-ttu-id="10a75-121">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="10a75-121">Click **OK** to close the dialog.</span></span>

7. <span data-ttu-id="10a75-122">Para compilar la solución, presione Ctrl+MAYÚS+B.</span><span class="sxs-lookup"><span data-stu-id="10a75-122">To build the solution, press CTRL+SHIFT+B.</span></span>

8. <span data-ttu-id="10a75-123">Para ejecutar la solución, presione CTRL+F5.</span><span class="sxs-lookup"><span data-stu-id="10a75-123">To run the solution, press CTRL+F5.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="10a75-124">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="10a75-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="10a75-125">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="10a75-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="10a75-126">Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="10a75-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="10a75-127">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="10a75-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\NetDcSasDcSwithDCR`  
