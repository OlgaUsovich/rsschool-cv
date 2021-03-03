# Volha Usovich
### Junior Developer  

    tel. +375 29 9565153
    e-mail: olya.usovich@mail.ru

## Summary

I'm at the stage of *learning* programming now. My main purpose is to get new new knowledge and improve my skills with new technologies and programming languages. My **strong point** is that I quite quickly understand the educational materials.  
Now I work as a systems analyst. My main responsibilities are writing technical and supporting documentation, database administration (Postgres).

## Key skills

* Python
* Django
* Git
* PostreSQL
* HTML (using Bootstrap)
* Technical writing

## Примеры кода ([GitHub](https://github.com/OlgaUsovich/finalProject/ "view the project on GitHub"))

- Python
```python
@login_required
def show_history(request):
    user_info = request.user
    orders = Order.objects.filter(user=user_info)
    if 'page' in request.GET:
        page_num = request.GET['page']
    else:
        page_num = 1
    paginator = Paginator(orders, 5)
    pages = paginator.get_page(page_num)
    for order_ in orders:
        order_.sum = 0
        order_items = order_.items.all()
        for item in order_items:
            order_.sum += item.quantity * item.price
    return render(request, 'orders/order/orders_history.html', locals())
```
- HTML 
```html
<div class="container">
        <div style="padding-top: 10px; padding-bottom: 10px;">
            <a type="button" class="btn btn-dark" href="{% url 'products:list' %}">Вернуться на главную</a>
            <a type="button" class="btn btn-secondary" href="{% url 'authentication:profile' %}">Назад</a>
        </div>
        <div class="row">

            {% for order in pages %}
                <div class="col-lg-12" style="padding-bottom: 10px; padding-top: 10px;">
                    <h3 class="product-name"><strong>Заказ № {{ order.id }}</strong></h3>
                    <table class="table table-borderless">
                        <thead>
                        <tr>
                            <th scope="col" colspan="3" class="">
                                <b>Дата заказа: {{ order.created }}</b>
                            </th>
                        </tr>
                        <tr class="table-secondary">
                            <th scope="row">Наименование товара</th>
                            <th scope="row">Количество</th>
                            <th scope="row">Цена товара</th>
                        </tr>
                        </thead>
                        <tbody class="table-light">
                        <tr>
                            {% for item in order_.items.all %}
                                <td>{{ item.product }}</td>
                                <td>{{ item.quantity }}</td>
                                <td>{{ item.price }}</td>
                                </tr>

                                <tr>
                                    <th class="{% if forloop.last %}table-success{% endif %}" colspan="4">
                                        {% if forloop.last %}Общая сумма заказа: {{ order_.sum }}{% endif %}</th>
                                </tr>
                            {% endfor %}
                        </tbody>
                    </table>

                </div>
            {% empty %}
                <h5 class="product-name-detail">Вы еще ничего не заказывали.</h5>
            {% endfor %}
        </div>
```
- CSS
```css
@font-face {
    font-family: 'Playlist-Script';
    src: url('/static/Playlist-Script.ttf.woff') format('woff');
    font-weight: normal;
    font-style: normal;
}

.logo {
    margin-right: auto;
    text-decoration: none;
    font-family: "Playlist-Script";
    font-size: 38px;
    color: white;
}

.logo:hover{
    text-decoration: none;
    color: darkgray;
}
```
## Experience
- [Graduation Project for IT Academy Stormnet](https://github.com/OlgaUsovich/finalProject/ "view the project on GitHub")

## Education

### **Main education:**  

      Department of Economic Informatics
      Belarusion State Economic University (BSEU)
      Graduation - Jun. 2017


### **Courses:**  

      Python Programming & Django Framework
      IT Academy Stormnet
      Graduation - Feb. 2021

      Python Programming - Bioinformatics Institute
      Online course on Stepik.org
      Score - 100%
      Graduation - Dec. 2020

## Languages 
- English - B1
