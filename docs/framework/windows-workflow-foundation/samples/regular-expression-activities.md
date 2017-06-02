---
title: "Actividades de expresi&#243;n normales | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b8f24694-49db-4339-92ec-014e3d4ae63b
caps.latest.revision: 9
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 9
---
# Actividades de expresi&#243;n normales
En este ejemplo se muestra cómo crear un conjunto de actividades que exponen la funcionalidad de expresión regular del espacio de nombres <xref:System.Text.RegularExpressions>.Estas actividades personalizadas se pueden usar en una aplicación de flujo de trabajo.[!INCLUDE[crabout](../../../../includes/crabout-md.md)] las expresiones regulares, vea [System.Text.RegularExpressions \(Espacio de nombres\)](http://go.microsoft.com/fwlink/?LinkId=150434).  
  
 En la siguiente tabla se detallan las actividades personalizadas de este ejemplo.  
  
|Actividad|Descripción|  
|---------------|-----------------|  
|IsMatch|Especifica si la expresión regular encontró una coincidencia en la cadena de entrada.|  
|Matches|Busca todas las apariciones de una expresión regular en una cadena de entrada y devuelve todas las coincidencias correctas.|  
|Replace|Dentro de una cadena de entrada especificada, reemplaza cadenas que hacen coincidir un modelo de expresión regular con una cadena de reemplazo especificada.|  
  
## IsMatch  
 La actividad personalizada `IsMatch` devuelve `true` si la propiedad de cadena `Input` encuentra una coincidencia en la expresión regular especificada en la propiedad `Pattern`.La actividad se deriva de <xref:System.Activities.CodeActivity%601> y dentro del método <xref:System.Activities.CodeActivity%601.Execute%2A> llama al método <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>.  
  
 En la siguiente tabla se describen las propiedades y el valor devuelto para la actividad personalizada `IsMatch`.  
  
|Propiedad o valor devuelto|Descripción|  
|--------------------------------|-----------------|  
|Pattern \(necesario\)|La expresión regular con la que buscar.|  
|Input \(necesario\)|La cadena de entrada que se va a buscar.|  
|RegexOptions|Bit a bit O combinación de valores de enumeración [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446).|  
|Valor devuelto|`true` si la entrada encuentra una coincidencia en el modelo proporcionado; de lo contrario, `false`.|  
  
 En el siguiente ejemplo de código se muestra cómo utilizar la actividad personalizada `IsMatch`.  
  
```  
new IsMatch  
{  
    Pattern = new InArgument<string>( @"^-?\d+(\.\d{2})?$"),  
    Input = "20.00",  
};  
  
```  
  
## Matches  
 La actividad personalizada `Matches` busca todas las apariciones de una expresión regular en una cadena de entrada y devuelve todas las coincidencias correctas.La actividad se deriva de <xref:System.Activities.CodeActivity%601> y dentro del método <xref:System.Activities.CodeActivity%601.Execute%2A> llama al método <xref:System.Text.RegularExpressions.Regex.Matches%2A>.  
  
 En la siguiente tabla se describen las propiedades y el valor devuelto para la actividad personalizada `IsMatch`.  
  
|Propiedad o valor devuelto|Descripción|  
|--------------------------------|-----------------|  
|Pattern \(necesario\)|La expresión regular con la que buscar.|  
|Input \(necesario\)|La cadena de entrada que se va a buscar.|  
|RegexOptions|Bit a bit O combinación de valores de enumeración [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446).|  
|Valor devuelto|Un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene la colección de coincidencias correctas.|  
  
 En el siguiente ejemplo de código se muestra cómo utilizar la actividad personalizada `Matches`.  
  
```  
new Matches  
{  
    Pattern = @"\b(?<word>\w+)\s+(\k<word>)\b",  
    Input = "The quick brown fox  fox jumped over over the lazy dog dog.",  
};  
  
```  
  
## Replace  
 La actividad personalizada `Replace` busca una cadena de entrada y reemplaza todas las cadenas que hacen coincidir una expresión regular especificada con una cadena.La actividad se deriva de <xref:System.Activities.CodeActivity%601> y dentro del método <xref:System.Activities.CodeActivity%601.Execute%2A> llama al método <xref:System.Text.RegularExpressions.Regex.Replace%2A>.  
  
 En la siguiente tabla se describen las propiedades y el valor devuelto para la actividad personalizada `Replace`.  
  
|Propiedad o valor devuelto|Descripción|  
|--------------------------------|-----------------|  
|Pattern \(necesario\)|La expresión regular con la que buscar.|  
|Input \(necesario\)|La cadena de entrada que se va a buscar.|  
|Replacement|La cadena de reemplazo.<br /><br /> Si se establece `Replacement`, se omite la propiedad `MatchEvaluator`.Es necesario establecer la propiedad `Replacement` o `MatchEvaluator`.|  
|MatchEvaluator|Un método personalizado que examina cada coincidencia y devuelve la cadena coincidente original o una cadena de reemplazo.<br /><br /> Si se establece `Replacement`, se omite la propiedad `MatchEvaluator`.Es necesario establecer la propiedad `Replacement` o `MatchEvaluator`.|  
|RegexOptions|Bit a bit O combinación de valores de enumeración [RegexOptions](http://go.microsoft.com/fwlink/?LinkId=150446).|  
|Valor devuelto|Un objeto <xref:System.Text.RegularExpressions.MatchCollection> que contiene la colección de coincidencias correctas.|  
  
 En el siguiente ejemplo de código se muestra cómo utilizar la actividad personalizada `Replace`.  
  
```  
// Using the replacement string.  
new Replace  
{  
    Pattern = @"\bWorld\b",  
    Input = "Hello World! This is a wonderful World",  
    Replacement = "Universe"  
};  
  
// Using a match evaluator.  
new Replace  
{  
    Pattern = new InArgument<string>(pattern),  
    Input = new InArgument<string>(input),  
    MatchEvaluator = new MatchEvaluator(CapText)                  
};  
  
```  
  
#### Para utilizar este ejemplo  
  
1.  Abra el archivo de solución RegexActivities.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl\+MAYÚS\+B.  
  
3.  Para ejecutar la solución, presione CTRL\+F5.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo.Compruebe el siguiente directorio \(predeterminado\) antes de continuar.  
>   
>  `<>InstallDrive:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página de [ejemplos de Windows Communication Foundation \(WCF\) y Windows Workflow Foundation \(WF\) Samples para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)].Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<unidadDeInstalación>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\Regex`  
  
## Vea también