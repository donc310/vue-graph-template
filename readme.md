# Vue Graph Template

## ABOUT

###

The Template is a [Vue.js](https://vuejs.org) app which uses [ngraph.graph](https://github.com/anvaka/ngraph.graph) a Library which implements an API to modify graph structure and supports event-driven notifications when graph changes.

The main component of the template is [App.vue](src/components/core/App.vue).


### Youtube example available:

LINK : <a href="https://ngraph-youtube.herokuapp.com/#?q=baby">https://ngraph-youtube.herokuapp.com</a>

REPO:  <a href="https://github.com/donc310/vue-graph-youtube">https://github.com/donc310/vue-graph-youtube</a>


### Amazon example available:

LINK : <a href="https://ngraph-amazon.herokuapp.com/#?q=books">https://ngraph-amazon.herokuapp.com/#?q=books</a>

REPO:  <a href="https://github.com/donc310/vue-graph-amazon">https://github.com/donc310/vue-graph-amazon</a>

### HOW TO USE:

1. Clone this Repo 

3. install dependencies  using `npm install`

3. Create an `App.vue` file in in src/components/app which will be  the entry point of your app 

4. Import   `EventBus`  from  `src/component/util/event.js`

5. then either build or serve your app using 
#### Compiles and hot-reloads for development
```
npm run serve
```
OR
#### Compiles and minifies for production

```
npm run build
```



## Events and props

```html
<graph-component :fileName="fileName" 
                  :client="client">
                  :origin="origin"
<!-- other template stuff goes here -->
</graph-component>
```

### Props


#### `client` 
type: *String*

default: `json`


The type of client which the app should use. Possible values: `json` or `youtube` 


#### `fileName` 
type: *String*

default: `data`


Name of the Json File if `client` is   `json`


#### `origin` 
type: *String*

default: `"api/v1/graphdata"`

The Url path 



### Events

Events are emitted from the  [GraphView.vue](src/components/core/App.vue) component using An EventBus.

An EventBus is a mode of transportation for one component to pass props from one component to another

no matter where those components are located in the tree. To Listen to changes from the Main component you should 

#1 import EventBus into your component using 
```
import EventBus from "@/lib/util/event";

```


#2 Listen to events on your Mounted Hook

```

mounted() {
   EventBus.$on("CORE::NODE_SELECTED", selected_node => {});
   EventBus.$on("CORE::NODES_UPDATE", NODES => {});
}

```




#### `"CORE::BEFORE_INIT"`

Fired before the graph is initiated

#### `"CORE::NODE_SELECTED"`

emits: `{ Node }`

Fired when a node is clicked.

#### `"CORE::NODES_UPDATE"`

emits: `{Nodes}`

Fired when the nodes change

#### `"CORE::BEFORE_DISPOSE"`

Fired before the graph is disposed.

---


<a href="http://www.africau.edu/images/default/sample.pdf"></a>
