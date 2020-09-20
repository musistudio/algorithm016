* 递归法:

  ```javascript
  var preorder = function(root) {
      let res = [];
      root && res.push(root.val)
      if(root && root.children) {
          for(let i=0;i<root.children.length;i++) {
              res = res.concat(preorder(root.children[i]))
          }
      }
      return res;
  };
  ```

* 迭代法:

  ```javascript
  var preorder = function(root) {
    if(!root) return [];
    let stack = [root], output = [];
    while(stack.length) {
      let node = stack.pop();
      if(node) {
          output.push(node.val);
          if(node.children && node.children.length) {
              stack.push(...node.children.reverse())
          }
      }
    }
    return output;
  };
  ```