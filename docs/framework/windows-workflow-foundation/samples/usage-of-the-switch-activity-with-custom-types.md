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
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2fbf80f0038ad830ab35fdb55272e45d8a6bffdc
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="usage-of-the-switch-activity-with-custom-types"></a>Usar la actividad Switch con tipos personalizados
En este ejemplo se describe cómo habilitar una actividad <xref:System.Activities.Statements.Switch%601> para evaluar un tipo complejo definido por el usuario en tiempo de ejecución. En los lenguajes de programación de procedimientos más tradicionales, un [cambiar](http://go.microsoft.com/fwlink/?LinkId=180521) instrucción selecciona una lógica de ejecución basándose en la evaluación condicional de una variable. Tradicionalmente, una instrucción `switch` funciona en una expresión que se puede evaluar estáticamente. Por ejemplo, en C# esto significa que solo se admiten los tipos primitivos, como <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, y los tipos de enumeración.  
  
 Para habilitar el cambio en una clase personalizada, se debe implementar lógica que evalúe los valores del tipo complejo personalizado en tiempo de ejecución. En este ejemplo se muestra cómo habilitar el cambio en un tipo complejo personalizado denominado `Person`.  
  
-   En la clase `Person` personalizada, se declara un atributo <xref:System.ComponentModel.TypeConverter> con el nombre de la clase <xref:System.ComponentModel.TypeConverter> personalizada.  
  
    ```  
    [TypeConverter(typeof(PersonConverter))]  
    public class Person  
    {  
       public string Name { get; set; }  
       public int Age { get; set; }  
    ...  
    ```  
  
-   En la clase `Person` personalizada, se invalidan los métodos <xref:System.Object.Equals%2A> y <xref:System.Object.GetHashCode%2A>.  
  
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
  
-   Se implementa una clase <xref:System.ComponentModel.TypeConverter> personalizada que realiza la conversión de una instancia de la clase personalizada a una cadena y una cadena a una instancia de una clase personalizada.  
  
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
  
 Este ejemplo incluye los siguientes archivos.  
  
-   **Person.cs**: define la `Person` clase.  
  
-   **PersonConverter.cs**: el convertidor de tipos para la `Person` clase.  
  
-   **Sequence.XAML**: un flujo de trabajo que cambia el `Person` tipo.  
  
-   **Program.cs**: la función principal que se ejecuta el flujo de trabajo.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Cargue Switch.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Presione Ctrl+MAYÚS+B para compilar la solución.  
  
3.  Presione CTRL + F5 para ejecutar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## <a name="see-also"></a>Vea también  
 [Biblioteca de actividades integrada](../../../../docs/framework/windows-workflow-foundation/net-framework-4-5-built-in-activity-library.md)
