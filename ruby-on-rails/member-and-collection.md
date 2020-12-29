# member와 collection
routing에서의 member와 collection의 개념
## member
ID를 필요로 한다. 
```ruby
Rails.application.routes.draw do
  resources :homes do
    get :post, on: :member
  end
end
```
**Prefix**  
`post_home` (singular)  
**URI Pattern**  
`/homes/:id/post(.:format)`  
**Controller#Action**  
`homes#post`
## collection
ID를 필요로 하지 않는다. 
```ruby
Rails.application.routes.draw do
  resources :homes do
    get :post, on: :collection
  end
end
```
**Prefix**  
`post_homes` (plural)  
**URI Pattern**  
`/homes/post(.:format)`  
**Controller#Action**  
`homes#post`

---
출처 : https://medium.com/@tadhao/member-vs-collection-in-rails-routes-ade10c8c5d19