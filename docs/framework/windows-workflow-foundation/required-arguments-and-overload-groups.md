---
title: Argumentos necesarios y grupos de sobrecarga
ms.date: 03/30/2017
ms.assetid: 4ca3ed06-b9af-4b85-8b70-88c2186aefa3
ms.openlocfilehash: 4eb62306f52b8ff890d5a5333c3789bd84ad7f60
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79142945"
---
# <a name="required-arguments-and-overload-groups"></a>Argumentos necesarios y grupos de sobrecarga
Se pueden configurar las actividades de manera que sea necesario enlazar algunos argumentos para que la actividad pueda ejecutarse. El atributo `RequiredArgument` se usa para indicar que se necesitan algunos argumentos en una actividad mientras que el atributo `OverloadGroup` se usa para agrupar categorías de argumentos necesarios. Al usar los atributos, los autores de actividades pueden proporcionar configuraciones simples o complejas de validación de actividades.  
  
## <a name="using-required-arguments"></a>Usar argumentos necesarios  
 Para usar el atributo `RequiredArgument` en una actividad, indique los argumentos que desee mediante <xref:System.Activities.RequiredArgumentAttribute>. En este ejemplo, una actividad `Add` se define con dos argumentos necesarios.  
  
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
  
 En XAML, los argumentos necesarios también se indican mediante <xref:System.Activities.RequiredArgumentAttribute>. En este ejemplo, la actividad `Add` se define con tres argumentos y usa una actividad <xref:System.Activities.Statements.Assign%601> para realizar la operación de suma.  
  
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
  
 Si se usa la actividad y no se enlaza ninguno de los argumentos necesarios, se devuelve el siguiente error de validación.  
  
 **No se proporcionó el valor para un argumento de actividad necesario 'Operand1'.**  
> [!NOTE]
> Para obtener más información sobre cómo comprobar y controlar errores y advertencias de validación, vea [Invocar validación](invoking-activity-validation.md)de actividad .  
  
## <a name="using-overload-groups"></a>Usar grupos de sobrecargas

Los grupos de sobrecargas proporcionan un método para indicar qué combinaciones de argumentos son válidas en una actividad. Los argumentos se agrupan mediante <xref:System.Activities.OverloadGroupAttribute>. A cada grupo se le asigna <xref:System.Activities.OverloadGroupAttribute>un nombre especificado por el archivo . La actividad es válida cuando solo se enlaza un conjunto de argumentos en un grupo de sobrecarga. En el ejemplo siguiente, se define una clase `CreateLocation`.  
  
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
  
 El objetivo de esta actividad es especificar una ubicación en los EE. UU. Para ello, el usuario de la actividad puede especificar la ubicación con uno de los tres grupos de argumentos. Para especificar las combinaciones válidas de argumentos, se definen tres grupos de sobrecargas. `G1` contiene los argumentos `Latitude` y `Longitude`. `G2` contiene `Street`, `City` y `State`. `G3` contiene `Street` y `Zip`. `Name` también es un argumento necesario, pero no forma parte de un grupo de sobrecargas. Para que esta actividad sea válida, `Name` tendría que estar enlazado con todos los argumentos de uno y solo un grupo de sobrecargas.  
  
 En el ejemplo siguiente, tomado del ejemplo Actividades de `ConnectionString` acceso `ConfigFileSectionName`a [la base](./samples/database-access-activities.md) de datos, hay dos grupos de sobrecarga: y . Para que esta actividad sea válida, los argumentos `ProviderName` y `ConnectionString` deben estar enlazados, o el argumento `ConfigName`, pero no ambos.  
  
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
  
 Al definir un grupo de sobrecargas:  
  
- Un grupo de sobrecargas no puede ser un subconjunto o un conjunto equivalente de otro grupo de sobrecargas.  
  
    > [!NOTE]
    > Hay una excepción para esta regla. Si un grupo de sobrecargas es un subconjunto de otro grupo de sobrecargas y el subconjunto solo contiene argumentos donde `RequiredArgument` es `false`, el grupo de sobrecargas es válido.  
  
- Los grupos de sobrecargas se pueden superponer pero es un error si la intersección de los grupos contiene todos los argumentos necesarios de uno o ambos grupos de sobrecargas. En el ejemplo anterior los grupos de sobrecargas `G2` y `G3` se superponían, pero como la intersección no contenía todos los argumentos de uno o ambos grupos, era válido.  
  
 Al enlazar argumentos en un grupo de sobrecargas:  
  
- Se considera que un grupo de sobrecargas está enlazado si se enlazan todos los argumentos `RequiredArgument` en el grupo.  
  
- Si un grupo no tiene ningún argumento `RequiredArgument` pero tiene enlazado al menos uno, se considera que el grupo está enlazado.  
  
- Es un error de validación si no se enlaza ningún grupo de sobrecargas a menos que un grupo de sobrecargas no tenga ningún argumento `RequiredArgument`.  
  
- Es un error tener enlazado más de un grupo de sobrecargas; es decir, se enlazan todos los argumentos necesarios en un grupo de sobrecargas y también se enlaza cualquier argumento en otro grupo de sobrecargas.
