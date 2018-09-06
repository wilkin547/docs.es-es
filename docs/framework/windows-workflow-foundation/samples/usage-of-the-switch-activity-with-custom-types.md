---
title: Usar la actividad Switch con tipos personalizados
ms.date: 03/30/2017
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
ms.openlocfilehash: b24a03573b31f3fb1c34d4aa6e03bc11f5b25455
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44038879"
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a><span data-ttu-id="058c9-102">Usar la actividad Switch con tipos personalizados</span><span class="sxs-lookup"><span data-stu-id="058c9-102">Usage of the Switch Activity with Custom Types</span></span>
<span data-ttu-id="058c9-103">En este ejemplo se describe cómo habilitar una actividad <xref:System.Activities.Statements.Switch%601> para evaluar un tipo complejo definido por el usuario en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="058c9-103">This sample describes how to enable a <xref:System.Activities.Statements.Switch%601> activity to evaluate a user-defined complex type at runtime.</span></span> <span data-ttu-id="058c9-104">En los lenguajes de programación de procedimientos más tradicionales, un [cambiar](https://go.microsoft.com/fwlink/?LinkId=180521) instrucción selecciona una lógica de ejecución según la evaluación condicional de una variable.</span><span class="sxs-lookup"><span data-stu-id="058c9-104">In most traditional procedural programming languages, a [switch](https://go.microsoft.com/fwlink/?LinkId=180521) statement selects an execution logic based on the conditional evaluation of a variable.</span></span> <span data-ttu-id="058c9-105">Tradicionalmente, una instrucción `switch` funciona en una expresión que se puede evaluar estáticamente.</span><span class="sxs-lookup"><span data-stu-id="058c9-105">Traditionally, a `switch` statement operates on an expression that can be statically evaluated.</span></span> <span data-ttu-id="058c9-106">Por ejemplo, en C# esto significa que solo se admiten los tipos primitivos, como <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, y los tipos de enumeración.</span><span class="sxs-lookup"><span data-stu-id="058c9-106">For example, in C# this means that only primitive types, such as <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, and enumeration types are supported.</span></span>  
  
 <span data-ttu-id="058c9-107">Para habilitar el cambio en una clase personalizada, se debe implementar lógica que evalúe los valores del tipo complejo personalizado en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="058c9-107">To enable switching on a custom class, logic must be implemented to evaluate values of the custom complex type at runtime.</span></span> <span data-ttu-id="058c9-108">En este ejemplo se muestra cómo habilitar el cambio en un tipo complejo personalizado denominado `Person`.</span><span class="sxs-lookup"><span data-stu-id="058c9-108">This sample demonstrates how to enable switching on a custom complex type named `Person`.</span></span>  
  
-   <span data-ttu-id="058c9-109">En la clase `Person` personalizada, se declara un atributo <xref:System.ComponentModel.TypeConverter> con el nombre de la clase <xref:System.ComponentModel.TypeConverter> personalizada.</span><span class="sxs-lookup"><span data-stu-id="058c9-109">In the custom class `Person`, a <xref:System.ComponentModel.TypeConverter> attribute is declared with the name of the custom <xref:System.ComponentModel.TypeConverter>.</span></span>  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   <span data-ttu-id="058c9-110">En la clase `Person` personalizada, se invalidan los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A>.</span><span class="sxs-lookup"><span data-stu-id="058c9-110">In the custom class `Person`, the <xref:System.Object.Equals%2A> and <xref:System.Object.GetHashCode%2A> classes are overridden.</span></span>  
  
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
  
-   <span data-ttu-id="058c9-111">Se implementa una clase <xref:System.ComponentModel.TypeConverter> personalizada que realiza la conversión de una instancia de la clase personalizada a una cadena y una cadena a una instancia de una clase personalizada.</span><span class="sxs-lookup"><span data-stu-id="058c9-111">A custom <xref:System.ComponentModel.TypeConverter> class is implemented that performs the conversion of an instance of the custom class to a string and a string to an instance of a custom class.</span></span>  
  
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
  
 <span data-ttu-id="058c9-112">Este ejemplo incluye los siguientes archivos.</span><span class="sxs-lookup"><span data-stu-id="058c9-112">The following files are included in this sample:</span></span>  
  
-   <span data-ttu-id="058c9-113">**Person.cs**: define el `Person` clase.</span><span class="sxs-lookup"><span data-stu-id="058c9-113">**Person.cs**: Defines the `Person` class.</span></span>  
  
-   <span data-ttu-id="058c9-114">**PersonConverter.cs**: el convertidor de tipos para el `Person` clase.</span><span class="sxs-lookup"><span data-stu-id="058c9-114">**PersonConverter.cs**: The type converter for the `Person` class.</span></span>  
  
-   <span data-ttu-id="058c9-115">**Sequence.XAML**: un flujo de trabajo que se cambia los `Person` tipo.</span><span class="sxs-lookup"><span data-stu-id="058c9-115">**Sequence.xaml**: a workflow that switches over the `Person` type.</span></span>  
  
-   <span data-ttu-id="058c9-116">**Program.cs**: la función principal que se ejecuta el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="058c9-116">**Program.cs**: The main function that runs the workflow.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="058c9-117">Para utilizar este ejemplo</span><span class="sxs-lookup"><span data-stu-id="058c9-117">To use this sample</span></span>  
  
1.  <span data-ttu-id="058c9-118">Cargue Switch.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span><span class="sxs-lookup"><span data-stu-id="058c9-118">Load Switch.sln in [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].</span></span>  
  
2.  <span data-ttu-id="058c9-119">Presione Ctrl+MAYÚS+B para compilar la solución.</span><span class="sxs-lookup"><span data-stu-id="058c9-119">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
3.  <span data-ttu-id="058c9-120">Presione CTRL + F5 para ejecutar el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="058c9-120">Press CTRL + F5 to run the sample.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="058c9-121">Puede que los ejemplos ya estén instalados en su equipo.</span><span class="sxs-lookup"><span data-stu-id="058c9-121">The samples may already be installed on your machine.</span></span> <span data-ttu-id="058c9-122">Compruebe el siguiente directorio (predeterminado) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="058c9-122">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="058c9-123">Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos.</span><span class="sxs-lookup"><span data-stu-id="058c9-123">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="058c9-124">Este ejemplo se encuentra en el siguiente directorio.</span><span class="sxs-lookup"><span data-stu-id="058c9-124">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a><span data-ttu-id="058c9-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="058c9-125">See Also</span></span>  
 [<span data-ttu-id="058c9-126">Biblioteca de actividades integrada</span><span class="sxs-lookup"><span data-stu-id="058c9-126">Built-In Activity Library</span></span>](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
