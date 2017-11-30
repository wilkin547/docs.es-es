---
title: Usar la actividad Switch con tipos personalizados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
caps.latest.revision: "10"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: a8a4418c582d00f1163305ce5d63c63c198dbc30
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a><span data-ttu-id="4f139-102">Usar la actividad Switch con tipos personalizados</span><span class="sxs-lookup"><span data-stu-id="4f139-102">Usage of the Switch Activity with Custom Types</span></span>
<span data-ttu-id="4f139-103">Este ejemplo describe cómo habilitar una <!--zz <xref:System.Activities. Statements.Switch`1>--> `xref:System.Activities` Statements.Switch`1?qualifyHint=False&autoUpgrade=True activity to evaluate a user-defined complex type at runtime. In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable. Traditionally, a \`cambiar ' instrucción funciona en una expresión que se puede evaluar estáticamente.</span><span class="sxs-lookup"><span data-stu-id="4f139-103">This sample describes how to enable a <!--zz <xref:System.Activities. Statements.Switch`1>--> `xref:System.Activities` Statements.Switch`1?qualifyHint=False&autoUpgrade=True activity to evaluate a user-defined complex type at runtime. In most traditional procedural programming languages, a [switch](http://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable. Traditionally, a `switch` statement operates on an expression that can be statically evaluated.</span></span> <span data-ttu-id="4f139-104">Por ejemplo, en C# esto significa que solo se admiten los tipos primitivos, como <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, y los tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="4f139-104">For example, in C# this means that only primitive types, such as <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, and enumeration types are supported.</span></span>  
  
 <span data-ttu-id="4f139-105">Para habilitar el cambio en una clase personalizada, se debe implementar lógica que evalúe los valores del tipo complejo personalizado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4f139-105">To enable switching on a custom class, logic must be implemented to evaluate values of the custom complex type at runtime.</span></span> <span data-ttu-id="4f139-106">En este ejemplo se muestra cómo habilitar el cambio en un tipo complejo personalizado denominado `Person`.</span><span class="sxs-lookup"><span data-stu-id="4f139-106">This sample demonstrates how to enable switching on a custom complex type named `Person`.</span></span>  
  
-   <span data-ttu-id="4f139-107">En la clase `Person` personalizada, se declara un atributo <xref:System.ComponentModel.TypeConverter> con el nombre de la clase <xref:System.ComponentModel.TypeConverter> personalizada.</span><span class="sxs-lookup"><span data-stu-id="4f139-107">In the custom class `Person`, a <xref:System.ComponentModel.TypeConverter> attribute is declared with the name of the custom <xref:System.ComponentModel.TypeConverter>.</span></span>  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   <span data-ttu-id="4f139-108">En la clase `Person` personalizada, se invalidan los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="4f139-108">In the custom class `Person`, the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> classes are overridden.</span></span>  
  
    ```  
    public override bool Equals(object obj)  
    {  
        Person person = obj as Person;  
  
        if (person != null)  
        {  
            return string.Equals(this.Name, person.Name);  
        }  
  
        return false;  
    }  
  
    public override int GetHashCode()  
    {  
        if (this.Name != null)  
        {  
            return this.Name.GetHashCode();  
        }  
  
        return 0;  
    }  
    ```  
  
-   <span data-ttu-id="4f139-109">Se implementa una clase <xref:System.ComponentModel.TypeConverter> personalizada que realiza la conversión de una instancia de la clase personalizada a una cadena y una cadena a una instancia de una clase personalizada.</span><span class="sxs-lookup"><span data-stu-id="4f139-109">A custom <xref:System.ComponentModel.TypeConverter> class is implemented that performs the conversion of an instance of the custom class to a string and a string to an instance of a custom class.</span></span>  
  
    ```  
    public class PersonConverter : TypeConverter  
    {  
        public override bool CanConvertFrom(ITypeDescriptorContext context,  
           Type sourceType)  
        {  
            return (sourceType is string);  
        }  
  
        // Overrides the ConvertFrom method of TypeConverter.  
        public override object ConvertFrom(ITypeDescriptorContext context,  
           CultureInfo culture, object value)  
        {  
            if (value == null)  
            {  
                return null;  
            }  
  
            if (value is string)  
            {  
                return new Person  
                {  
                    Name = (string)value  
                };  
            }  
  
            return base.ConvertFrom(context, culture, value);  
        }  
  
        // Overrides the ConvertTo method of TypeConverter.  
        public override object ConvertTo(ITypeDescriptorContext context,  
           CultureInfo culture, object value, Type destinationType)  
        {  
            if (destinationType == typeof(string))  
            {  
                if (value != null)  
                {  
                    return ((Person) value).Name;  
                }  
                else  
                {  
                    return null;  
                }  
            }  
  
            return base.ConvertTo(context, culture, value, destinationType);  
        }  
    }  
    ```  
  
 <span data-ttu-id="4f139-110">Este ejemplo incluye los siguientes archivos.</span><span class="sxs-lookup"><span data-stu-id="4f139-110">The following files are included in this sample:</span></span>  
  
-   <span data-ttu-id="4f139-111">**Person.cs**: define la `Person` clase.</span><span class="sxs-lookup"><span data-stu-id="4f139-111">**Person.cs**: Defines the `Person` class.</span></span>  
  
-   <span data-ttu-id="4f139-112">**PersonConverter.cs**: el convertidor de tipos para la `Person` clase.</span><span class="sxs-lookup"><span data-stu-id="4f139-112">**PersonConverter.cs**: The type converter for the `Person` class.</span></span>  
  
-   <span data-ttu-id="4f139-113">**Sequence.XAML**: un flujo de trabajo que cambia el `Person` tipo.</span><span class="sxs-lookup"><span data-stu-id="4f139-113">**Sequence.xaml**: a workflow that switches over the `Person` type.</span></span>  
  
-   <span data-ttu-id="4f139-114">**Program.cs**: la función principal que se ejecuta el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="4f139-114">**Program.cs**: The main function that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="4f139-115">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="4f139-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="4f139-116">Cargue Switch.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4f139-116">Load Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="4f139-117">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="4f139-117">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="4f139-118">Presione CTRL + F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4f139-118">Press CTRL + F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4f139-119">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="4f139-119">The samples may already be installed on your machine.</span></span> <span data-ttu-id="4f139-120">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="4f139-120">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="4f139-121">Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="4f139-121">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="4f139-122">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="4f139-122">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a><span data-ttu-id="4f139-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f139-123">See Also</span></span>  
 [<span data-ttu-id="4f139-124">Biblioteca de actividades integrada</span><span class="sxs-lookup"><span data-stu-id="4f139-124">Built-In Activity Library</span></span>](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
