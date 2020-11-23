###This is an explanation of how to use "singular" and "plural" properly in Rails.

## question

For example, "blogs" is specified for parameters when creating a controller, and "blog" is specified for parameters when creating a model. It seems that various variables are automatically created based on that, so I think it makes sense to use "blogs" and "blog" properly, but it is still confusing because there is no description anywhere.  <br/>

Even if I try "rake routes", there are "blog" "new_blog" "blogs" and "confirm_blogs" in Prefix. I don't understand why this is happening at all.  <br/>

## answer

thank your for a good question,you are almost there.<br/>
but let me clarify some things to you.<br/>

the reason why these things happen is due to what they call ruby naming convention lemmi walk you through it.

## General Ruby conventions ##

Class names are `CamelCase`.<br/>

Methods and variables are `snake_case`.<br/>

### let's consider database.

*Database tables* use `snake_case`. Table names are **plural**.<br/>

*Column names* in the database use `snake_case`, but are generally **singular**.<br/>

### let's consider now model.

Model *class names* use `CamelCase`. These are **singular**, and will map automatically to the plural database table name.<br/>

Model *attributes* and *methods* use `snake_case` and match the column names in the database.<br/>

Model files go in `app/models/#{singular_model_name}.rb`.<br/>

and back to your question thet is why "blog" is specified for parameters when creating a model.<br/>

### let's consider now controllers.

Controller *class names* use `CamelCase` and have `Controller` as a suffix. The `Controller` suffix is always singular. The name of the resource is usually **plural**.

Controller *actions* use `snake_case` and usually match the standard route names Rails defines (`index`, `show`, `new`, `create`, `edit`, `update`, `delete`).

Controller files go in `app/controllers/#{resource_name}_controller.rb`.

back to your question thet is why "blogs" is specified for parameters when creating a controller.<br/>

### let's consider now controllers.

Route names are `snake_case`, and usually match the controller. Most of the time routes are **plural** and use the plural `resources`.

[Singular routes](http://edgeguides.rubyonrails.org/routing.html#singular-resources) are a special case. These use the singular `resource` and a singular resource name. However, they still map to a plural controller by default!

and this explains why in rake "routes" there are "blog" "new_blog" "blogs" and "confirm_blogs" in Prefix.<br/>

let me hope the answer was helpful. thank you.<br/>