---
title: "Usar la actividad Switch con tipos personalizados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 482a48c4-eb83-40c3-a4e2-2f9a8af88b75
caps.latest.revision: 10
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 10
---
# Usar la actividad Switch con tipos personalizados
En este ejemplo se describe cómo habilitar una actividad <xref:System.Activities.> Statements.Switch`1?qualifyHint=False&autoUpgrade=True para evaluar un tipo complejo definido por el usuario en tiempo de ejecución.En los lenguajes de programación orientados a procedimientos más tradicionales, una instrucción [switch](http://go.microsoft.com/fwlink/?LinkId=180521) selecciona una lógica de ejecución basada en la evaluación condicional de una variable.Tradicionalmente, una instrucción `switch` funciona en una expresión que se puede evaluar estáticamente.Por ejemplo, en C\# esto significa que solo se admiten los tipos primitivos, como <xref:System.Boolean>, <xref:System.Int32>, <xref:System.String>, y los tipos de enumeración.  
  
 Para habilitar el cambio en una clase personalizada, se debe implementar lógica que evalúe los valores del tipo complejo personalizado en tiempo de ejecución.En este ejemplo se muestra cómo habilitar el cambio en un tipo complejo personalizado denominado `Person`.  
  
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
  
-   **Person.cs**: define la clase `Person`.  
  
-   **PersonConverter.cs**: el convertidor de tipos de la clase `Person`.  
  
-   **Sequence.xaml**: flujo de trabajo que cambia el tipo de `Person`.  
  
-   **Program.cs**: la función principal que ejecuta el flujo de trabajo.  
  
#### Para utilizar este ejemplo  
  
1.  Cargue Switch.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Presione Ctrl\+MAYÚS\+B para compilar la solución.  
  
3.  Presione CTRL \+ F5 para ejecutar el ejemplo.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[wf1](../../../../includes/wf1-md.md)] y [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Basic\Built-InActivities\Switch`  
  
## Vea también  
 [Biblioteca de actividades integrada](../../../../docs/framework/windows-workflow-foundation//net-framework-4-5-built-in-activity-library.md)