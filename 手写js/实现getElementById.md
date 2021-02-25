```
	var body = document.body
	function find(node,id){
		for(let item in Array.from(node.childNodes)){
			if(item.id == id){
				return item
			}
			else{
				return find(item,id)
			}
		}
	}
```

有问题