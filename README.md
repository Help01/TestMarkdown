# TestMarkdown
```xml
<?xml version="1.0" encoding="utf-8"?>
<CodeSnippets xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
  <CodeSnippet Format="1.0.0">
    <Header>
      <Title>Класс компонента данных</Title>
      <Shortcut>comp</Shortcut>
      <Description>Шаблон компонента данных</Description>
      <SnippetTypes>
        <SnippetType>Expansion</SnippetType>
      </SnippetTypes>
    </Header>
    <Snippet>
      <Imports>
        <Import>
          <Namespace>Pixeye.Actors</Namespace>
        </Import>
      </Imports>
      <Declarations>
        <Literal>
          <ID>shortname</ID>
          <ToolTip>Имя компонента без суффиксов</ToolTip>
          <Default>Name</Default>
        </Literal>
        <Literal>
          <ID>namespace</ID>
          <ToolTip>Неймспэйс в котором находится класс компонента данных</ToolTip>
          <Default>Namespace</Default>
        </Literal>
      </Declarations>
      <Code Language="csharp">
        <![CDATA[
        public class Component$shortname$
        {
			$end$
        }
      
   #region HELPERS
   public static partial class Component
    {
     public const string $shortname$ = "$namespace$.Component$shortname$";
		internal static ref Component$shortname$ Component$shortname$(in this ent entity)
		=> ref Storage<Component$shortname$>.components[entity.id];
    }
    
   sealed class Storage$shortname$ : Storage<Component$shortname$>
     {
	     public override Component$shortname$ Create() => new Component$shortname$();
	     
	    public override void Dispose(indexes disposed)
		  {
			  foreach (var id in disposed)
			  {
				ref var component = ref components[id];
				//dispose (reset) logic
			  }
		  }
      
     }
    #endregion
	]]>
      </Code>
    </Snippet>
  </CodeSnippet>
</CodeSnippets>
```
Чтобы использовать сниппет, разместите файл с расширением .snippet по расположению *%USERPROFILE%\Documents\Visual Studio 2019\Code Snippets\Visual C#\My Code Snippets*. 
Руководство по [сниппетам](https://docs.microsoft.com/ru-ru/visualstudio/ide/walkthrough-creating-a-code-snippet?view=vs-2019 "Официальное руководство с msdn"). [(доп.)](https://professorweb.ru/my/programs/visual-studio/level2/2_17.php "Руководство на DoctorWeb").
