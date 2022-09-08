# React E-commerce
A React application with admin & user interfaces. The admin interface has a form where the admin add the product details. On the user interface there is the list with products added by admin. Products can be sorted by favorite product or all products.

# Install
npm install

## Run
npm start

# Quick Look

```
...
return (
    <>
      {activeComponent === "admin" ? (
        <Form
          name={name}
          setName={setName}
          price={price}
          setPrice={setPrice}
          size={size}
          setSize={setSize}
          description={description}
          setDescription={setDescription}
          image={image}
          setImage={setImage}
          products={products}
          setProducts={setProducts}
          addProduct={addProduct}
          activeComponent={activeComponent}
          setActiveComponent={setActiveComponent}
        />
      ) : (
        <>
          <button
            className="admin-btn"
            onClick={(e) => setActiveComponent("admin")}
          >
            Admin
          </button>

          <h2>We create art</h2>
          <div className="filter-btns">
            <button className="all-btn" onClick={(e) => setFilterTerm("All")}>
              All
            </button>
            <button
              className="fav-btn"
              onClick={(e) => setFilterTerm("<FaHeart/>")}
            >
              <FaHeart />
            </button>
          </div>

          <ul className="list-style">
            {Array.isArray(products)
              ? filterProducts().map((product) => {
                  return (
                    <Listing
                      key={product.id}
                      product={product}
                      products={products}
                      setProducts={setProducts}
                      image={image}
                      setImage={setImage}
                      activeComponent={activeComponent}
                      setActiveComponent={setActiveComponent}
                      favoriteProducts={favoriteProducts}
                    />
                  );
                })
              : null}
          </ul>
        </>
      )}
    </>
  );
  ```
