---
title: Argumentos necesarios y grupos de sobrecarga
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: 452285b1f5b73ecf75fc50f59365aa2633f26e42
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96245879"
---
# <a name="required-arguments-and-overload-groups"></a><span data-ttu-id="8b469-102">Argumentos necesarios y grupos de sobrecarga</span><span class="sxs-lookup"><span data-stu-id="8b469-102">Required Arguments and Overload Groups</span></span>

<span data-ttu-id="8b469-103">Se pueden configurar las actividades de manera que sea necesario enlazar algunos argumentos para que la actividad pueda ejecutarse.</span><span class="sxs-lookup"><span data-stu-id="8b469-103">Activities can be configured so that certain arguments are required to be bound for the activity to be valid for execution.</span></span> <span data-ttu-id="8b469-104">El atributo `RequiredArgument` se usa para indicar que se necesitan algunos argumentos en una actividad mientras que el atributo `OverloadGroup` se usa para agrupar categorías de argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="8b469-104">The `RequiredArgument` attribute is used to indicate that certain arguments on an activity are required and the `OverloadGroup` attribute is used to group categories of required arguments together.</span></span> <span data-ttu-id="8b469-105">Al usar los atributos, los autores de actividades pueden proporcionar configuraciones simples o complejas de validación de actividades.</span><span class="sxs-lookup"><span data-stu-id="8b469-105">By using the attributes, activity authors can provide simple or complex activity validation configurations.</span></span>  
  
## <a name="using-required-arguments"></a><span data-ttu-id="8b469-106">Usar argumentos necesarios</span><span class="sxs-lookup"><span data-stu-id="8b469-106">Using Required Arguments</span></span>  

 <span data-ttu-id="8b469-107">Para usar el atributo `RequiredArgument` en una actividad, indique los argumentos que desee mediante <xref:System.Activities.RequiredArgumentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8b469-107">To use the `RequiredArgument` attribute in an activity, indicate the desired arguments using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="8b469-108">En este ejemplo, una actividad `Add` se define con dos argumentos necesarios.</span><span class="sxs-lookup"><span data-stu-id="8b469-108">In this example, an `Add` activity is defined that has two required arguments.</span></span>  
  
```csharp  
public sealed class Add : CodeActivity<int>  
{  
    [RequiredArgument]  
    public InArgument<int> Operand1 { get; set; }  
  
    [RequiredArgument]  
    public InArgument<int> Operand2 { get; set; }  
  
    protected override int Execute(CodeActivityContext context)  
    {  
        return Operand1.Get(context) + Operand2.Get(context);  
    }  
}  
```  
  
 <span data-ttu-id="8b469-109">En XAML, los argumentos necesarios también se indican mediante <xref:System.Activities.RequiredArgumentAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8b469-109">In XAML, required arguments are also indicated by using <xref:System.Activities.RequiredArgumentAttribute>.</span></span> <span data-ttu-id="8b469-110">En este ejemplo, la actividad `Add` se define con tres argumentos y usa una actividad <xref:System.Activities.Statements.Assign%601> para realizar la operación de suma.</span><span class="sxs-lookup"><span data-stu-id="8b469-110">In this example the `Add` activity is defined by using three arguments and uses an <xref:System.Activities.Statements.Assign%601> activity to perform the add operation.</span></span>  
  
```xaml  
<Activity x:Class="ValidationDemo.Add" ...>  
  <x:Members>  
    <x:Property Name="Operand1" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Operand2" Type="InArgument(x:Int32)">  
      <x:Property.Attributes>  
        <RequiredArgumentAttribute />  
      </x:Property.Attributes>  
    </x:Property>  
    <x:Property Name="Result" Type="OutArgument(x:Int32)" />  
  </x:Members>  
  <Assign>  
    <Assign.To>  
      <OutArgument x:TypeArguments="x:Int32">[Result]</OutArgument>  
    </Assign.To>  
    <Assign.Value>  
      <InArgument x:TypeArguments="x:Int32">[Operand1 + Operand2]</InArgument>  
    </Assign.Value>  
  </Assign>  
</Activity>  
```  
  
 <span data-ttu-id="8b469-111">Si se usa la actividad y no se enlaza ninguno de los argumentos necesarios, se devuelve el siguiente error de validación.</span><span class="sxs-lookup"><span data-stu-id="8b469-111">If the activity is used and either of the required arguments is not bound the following validation error is returned.</span></span>  
  
 <span data-ttu-id="8b469-112">**No se proporcionó el valor para un argumento de actividad necesario 'Operand1'.**</span><span class="sxs-lookup"><span data-stu-id="8b469-112">**Value for a required activity argument 'Operand1' was not supplied.**</span></span>  
> [!NOTE]
> <span data-ttu-id="8b469-113">Para obtener más información sobre la comprobación y el control de errores y advertencias de validación, consulte [invocar la validación de actividad](invoking-activity-validation.md).</span><span class="sxs-lookup"><span data-stu-id="8b469-113">For more information about checking for and handling validation errors and warnings, see [Invoking Activity Validation](invoking-activity-validation.md).</span></span>  
  
## <a name="using-overload-groups"></a><span data-ttu-id="8b469-114">Usar grupos de sobrecargas</span><span class="sxs-lookup"><span data-stu-id="8b469-114">Using Overload Groups</span></span>

<span data-ttu-id="8b469-115">Los grupos de sobrecargas proporcionan un método para indicar qué combinaciones de argumentos son válidas en una actividad.</span><span class="sxs-lookup"><span data-stu-id="8b469-115">Overload groups provide a method for indicating which combinations of arguments are valid in an activity.</span></span> <span data-ttu-id="8b469-116">Los argumentos se agrupan mediante <xref:System.Activities.OverloadGroupAttribute>.</span><span class="sxs-lookup"><span data-stu-id="8b469-116">Arguments are grouped together by using <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="8b469-117">A cada grupo se le asigna un nombre especificado por <xref:System.Activities.OverloadGroupAttribute> .</span><span class="sxs-lookup"><span data-stu-id="8b469-117">Each group is given a name that is specified by the <xref:System.Activities.OverloadGroupAttribute>.</span></span> <span data-ttu-id="8b469-118">La actividad es válida cuando solo se enlaza un conjunto de argumentos de un grupo de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8b469-118">The activity is valid when only one set of arguments in an overload group are bound.</span></span> <span data-ttu-id="8b469-119">En el ejemplo siguiente, se define una clase `CreateLocation`.</span><span class="sxs-lookup"><span data-stu-id="8b469-119">In the following example, a `CreateLocation` class is defined.</span></span>  
  
```csharp  
class CreateLocation: Activity  
{  
    [RequiredArgument]  
    public InArgument<string> Name { get; set; }  
  
    public InArgument<string> Description { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Latitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G1")]  
    public InArgument<int> Longitude { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    [OverloadGroup("G3")]  
    public InArgument<string> Street { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> City { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G2")]  
    public InArgument<string> State { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("G3")]  
    public InArgument<int> Zip { get; set; }
}  
```  
  
 <span data-ttu-id="8b469-120">El objetivo de esta actividad es especificar una ubicación en los EE. UU.</span><span class="sxs-lookup"><span data-stu-id="8b469-120">The objective of this activity is to specify a location in the US.</span></span> <span data-ttu-id="8b469-121">Para ello, el usuario de la actividad puede especificar la ubicación con uno de los tres grupos de argumentos.</span><span class="sxs-lookup"><span data-stu-id="8b469-121">To do this, the user of the activity can specify the location using one of three groups of arguments.</span></span> <span data-ttu-id="8b469-122">Para especificar las combinaciones válidas de argumentos, se definen tres grupos de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8b469-122">To specify the valid combinations of arguments, three overload groups are defined.</span></span> <span data-ttu-id="8b469-123">`G1` contiene los argumentos `Latitude` y `Longitude`.</span><span class="sxs-lookup"><span data-stu-id="8b469-123">`G1` contains the `Latitude` and `Longitude` arguments.</span></span> <span data-ttu-id="8b469-124">`G2` contiene `Street`, `City` y `State`.</span><span class="sxs-lookup"><span data-stu-id="8b469-124">`G2` contains `Street`, `City`, and `State`.</span></span> <span data-ttu-id="8b469-125">`G3` contiene `Street` y `Zip`.</span><span class="sxs-lookup"><span data-stu-id="8b469-125">`G3` contains `Street` and `Zip`.</span></span> <span data-ttu-id="8b469-126">`Name` también es un argumento necesario, pero no forma parte de un grupo de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8b469-126">`Name` is also a required argument, but it is not part of an overload group.</span></span> <span data-ttu-id="8b469-127">Para que esta actividad sea válida, `Name` tendría que estar enlazado con todos los argumentos de uno y solo un grupo de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8b469-127">For this activity to be valid, `Name` would have to be bound together with all of the arguments from one and only one overload group.</span></span>  
  
 <span data-ttu-id="8b469-128">En el ejemplo siguiente, tomado del ejemplo de [actividades de acceso a bases de datos](./samples/database-access-activities.md) , hay dos grupos de sobrecargas: `ConnectionString` y `ConfigFileSectionName` .</span><span class="sxs-lookup"><span data-stu-id="8b469-128">In the following example, taken from the [Database Access Activities](./samples/database-access-activities.md) sample, there are two overload groups: `ConnectionString` and `ConfigFileSectionName`.</span></span> <span data-ttu-id="8b469-129">Para que esta actividad sea válida, los argumentos `ProviderName` y `ConnectionString` deben estar enlazados, o el argumento `ConfigName`, pero no ambos.</span><span class="sxs-lookup"><span data-stu-id="8b469-129">For this activity to be valid, either the `ProviderName` and `ConnectionString` arguments must be bound, or the `ConfigName` argument, but not both.</span></span>  
  
```csharp  
public class DbUpdate: AsyncCodeActivity  
{  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DefaultValue(null)]  
    public InArgument<string> ProviderName { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConnectionString")]  
    [DependsOn("ProviderName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConnectionString { get; set; }  
  
    [RequiredArgument]  
    [OverloadGroup("ConfigFileSectionName")]  
    [DefaultValue(null)]  
    public InArgument<string> ConfigName { get; set; }  
  
    [DefaultValue(null)]  
    public CommandType CommandType { get; set; }  
  
    [RequiredArgument]  
    public InArgument<string> Sql { get; set; }  
  
    [DependsOn("Sql")]  
    [DefaultValue(null)]  
    public IDictionary<string, Argument> Parameters { get; }  
  
    [DependsOn("Parameters")]  
    public OutArgument<int> AffectedRecords { get; set; }
}  
```  
  
 <span data-ttu-id="8b469-130">Al definir un grupo de sobrecargas:</span><span class="sxs-lookup"><span data-stu-id="8b469-130">When defining an overload group:</span></span>  
  
- <span data-ttu-id="8b469-131">Un grupo de sobrecargas no puede ser un subconjunto o un conjunto equivalente de otro grupo de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8b469-131">An overload group cannot be a subset or an equivalent set of another overload group.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="8b469-132">Hay una excepción para esta regla.</span><span class="sxs-lookup"><span data-stu-id="8b469-132">There is one exception to this rule.</span></span> <span data-ttu-id="8b469-133">Si un grupo de sobrecargas es un subconjunto de otro grupo de sobrecargas y el subconjunto solo contiene argumentos donde `RequiredArgument` es `false`, el grupo de sobrecargas es válido.</span><span class="sxs-lookup"><span data-stu-id="8b469-133">If an overload group is a subset of another overload group, and the subset contains only arguments where `RequiredArgument` is `false`, then the overload group is valid.</span></span>  
  
- <span data-ttu-id="8b469-134">Los grupos de sobrecargas se pueden superponer pero es un error si la intersección de los grupos contiene todos los argumentos necesarios de uno o ambos grupos de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8b469-134">Overload groups can overlap but it is an error if the intersection of the groups contains all the required arguments of one or both of the overload groups.</span></span> <span data-ttu-id="8b469-135">En el ejemplo anterior los grupos de sobrecargas `G2` y `G3` se superponían, pero como la intersección no contenía todos los argumentos de uno o ambos grupos, era válido.</span><span class="sxs-lookup"><span data-stu-id="8b469-135">In the previous example the `G2` and `G3` overload groups overlapped, but because the intersection did not contain all the arguments of one or both of the groups this was valid.</span></span>  
  
 <span data-ttu-id="8b469-136">Al enlazar argumentos en un grupo de sobrecargas:</span><span class="sxs-lookup"><span data-stu-id="8b469-136">When binding arguments in an overload group:</span></span>  
  
- <span data-ttu-id="8b469-137">Se considera que un grupo de sobrecargas está enlazado si se enlazan todos los argumentos `RequiredArgument` en el grupo.</span><span class="sxs-lookup"><span data-stu-id="8b469-137">An overload group is considered bound if all the `RequiredArgument` arguments in the group are bound.</span></span>  
  
- <span data-ttu-id="8b469-138">Si un grupo no tiene ningún argumento `RequiredArgument` pero tiene enlazado al menos uno, se considera que el grupo está enlazado.</span><span class="sxs-lookup"><span data-stu-id="8b469-138">If a group has zero `RequiredArgument` arguments and at least one argument bound, then the group is considered bound.</span></span>  
  
- <span data-ttu-id="8b469-139">Es un error de validación si no se enlaza ningún grupo de sobrecargas a menos que un grupo de sobrecargas no tenga ningún argumento `RequiredArgument`.</span><span class="sxs-lookup"><span data-stu-id="8b469-139">It is a validation error if no overload groups are bound unless one overload group has no `RequiredArgument` arguments in it.</span></span>  
  
- <span data-ttu-id="8b469-140">Es un error tener enlazado más de un grupo de sobrecargas; es decir, se enlazan todos los argumentos necesarios en un grupo de sobrecargas y también se enlaza cualquier argumento en otro grupo de sobrecargas.</span><span class="sxs-lookup"><span data-stu-id="8b469-140">It is an error to have more than one overload group bound, that is, all required arguments in one overload group are bound and any argument in another overload group is also bound.</span></span>
