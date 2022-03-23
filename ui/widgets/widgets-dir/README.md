# Instructions

Inside this folder, create a new React app using the below command:

`npx create-react-app my-app`

And inside this react app, make sure to create a folder named `bundle`, with a `bundle-descriptor.yaml` file and a `.ftl` file.

Replace `bundle-descriptor` with your desired name. And also give a name to your `.ftl` file, like `example.ftl`.

Inside the `bundle-descriptor.yaml` file add the following code:

```
code: cards-section
titles:
  en: Sample Cards Section Template
  it: Sample Cards Section Template
group: free
customUiPath: example.ftl
```

Keep the keys of the above code intact, but please change the values as per your project.

And inside the example.ftl file add this:

```
<#assign wp=JspTaglibs["/aps-core"]>
<#-- entando_resource_injection_point -->
<#-- Don't add anything above this line. The build scripts will automatically link the compiled JS and CSS for you and add them above this line so that the widget can be loaded-->

<@wp.info key="currentLang" var="currentLangVar" />
<cards-widget locale="${currentLangVar}"/>
```

Replace `cards-widget` with the name of your react app.
