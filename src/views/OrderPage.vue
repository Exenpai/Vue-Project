<template>
  <form method="post" v-on:submit.prevent="checkOrder">
    <fieldset>
      <legend>
        <h2>Contact Details</h2>
      </legend>
      <table class="center">
        <tr>
          <td>
            <label for="fullname">Full Name:</label>
          </td>
          <td>
            <input
              type="text"
              name="fullname"
              size="35"
              pattern="[A-Za-z\s]+"
              placeholder="Enter your first and last name here"
              required
              v-model="fullname"
            />
          </td>
        </tr>
        <tr>
          <td>
            <label for="address">Street Address:</label>
          </td>
          <td>
            <input
              type="text"
              name="address"
              size="35"
              pattern="([a-zA-Z0-9]| |/|\\|@|#|\$|%|&)+"
              placeholder="Enter your address here"
              required
              v-model="address"
            />
          </td>
        </tr>
        <tr>
          <td>
            <label for="phone">Telephone Number:</label>
          </td>
          <td>
            <input
              type="tel"
              name="phone"
              placeholder="000-000-0000"
              pattern="[0-9]{3}-[0-9]{3}-[0-9]{4}"
              required
              v-model="phone"
            />
          </td>
        </tr>
      </table>
    </fieldset>
    <fieldset>
      <legend>
        <h2>Pizza Choices</h2>
      </legend>
      <table>
        <tr>
          <td class=" center">
            <figure>
              <img
                src="https://images.contentstack.io/v3/assets/blt068dbc54bf4fc7ed/bltf70df0a3f7b98d04/5db5c829e9effa6ba52972ea/Triple_Cheese_Pizza_v2.jpg"
                height=" 75px"
                width="75px"
                alt="Picture of cheese pizza"
              />
              <figcaption>
                <input
                  type="radio"
                  name="pizzatype"
                  value="Super Cheesy"
                  v-model="picked_pizza"
                />Super Cheesy
              </figcaption>
            </figure>
          </td>
          <td class="center">
            <figure>
              <img
                src="https://www.queensleeappetit.com/wp-content/uploads/2019/02/Meat-Lovers-Pizza-6.jpg"
                height="75px"
                width="75px"
                alt="Picture of extra meaty pizza"
              />
              <figcaption>
                <input
                  type="radio"
                  name="pizzatype"
                  value="Extra Meaty"
                  v-model="picked_pizza"
                />Extra Meaty
              </figcaption>
            </figure>
          </td>
          <td class="center">
            <figure>
              <img
                src="https://usercontent2.hubstatic.com/14685585.jpg"
                height=" 75px"
                width="75px"
                alt="Picture of cheese pizza"
              />
              <figcaption>
                <input
                  type="radio"
                  name="pizzatype"
                  value="Really Veggy"
                  v-model="picked_pizza"
                />Really Veggy
              </figcaption>
            </figure>
          </td>
        </tr>
      </table>

      <table>
        <tr>
          <td>
            <input
              type="radio"
              name="pizzasize"
              value="Small"
              v-model="pizza_size"
            />Small $8.50
            <input
              type="radio"
              name="pizzasize"
              value="Medium"
              v-model="pizza_size"
            />Medium $11.50
            <input
              type="radio"
              name="pizzasize"
              value="Large"
              v-model="pizza_size"
            />Large $14.00
            <input
              type="radio"
              name="pizzasize"
              value="Extra Large"
              v-model="pizza_size"
            />Extra Large $16.50
          </td>
        </tr>
        <tr>
          <td>
            <label for="pizzaquantity">Quantity:</label>
            <input
              type="number"
              name="pizzaquantity"
              min="0"
              v-model="pizza_quantity"
            />
          </td>
        </tr>
      </table>
    </fieldset>
    <fieldset>
      <legend>
        <h2>Sandwich Choices (Choose one only one of these)</h2>
      </legend>
      <table>
        <table>
          <tr>
            <td class="center">
              <figure>
                <img
                  src="https://www.thegardengrazer.com/wp-content/uploads/2017/05/avo-sandwich.png"
                  height=" 75px"
                  width="75px"
                  alt="Picture of all garden vegetarian sandwich"
                />
                <figcaption>
                  <input
                    type="radio"
                    name="sandwich"
                    value="All Garden Vegetarian"
                    v-model="picked_sandwich"
                  />All Garden Vegetarian $7.50
                </figcaption>
              </figure>
            </td>
            <td class="center">
              <figure>
                <img
                  src="https://www.365daysofcrockpot.com/wp-content/uploads/2019/04/BBQ-Beef-Sandwiches.jpg"
                  height=" 75px"
                  width="75px"
                  alt="Picture of big beef on a bun"
                />
                <figcaption>
                  <input
                    type="radio"
                    name="sandwich"
                    value="Big Beef on a Bun"
                    v-model="picked_sandwich"
                  />Big Beef on a Bun $8.50
                </figcaption>
              </figure>
            </td>
          </tr>
        </table>

        <table>
          <tr>
            <td class="center">
              <figure>
                <img
                  src="https://assets.epicurious.com/photos/5620ffcf219057901cc67b64/master/pass/364812_grilled-cuban-sandwich_1x1.jpg"
                  height=" 75px"
                  width="75px"
                  alt="Picture of mixed grill sandwich"
                />
                <figcaption>
                  <input
                    type="radio"
                    name="sandwich"
                    value="Mixed Grill"
                    v-model="picked_sandwich"
                  />Mixed Grill $9.50
                </figcaption>
              </figure>
            </td>
            <td class="center">
              <figure>
                <img
                  src="https://www.thespruceeats.com/thmb/7mSTJ8amwWy1D-UFlciNuMLfv7Y=/960x0/filters:no_upscale():max_bytes(150000):strip_icc()/pulled-pork-and-slaw-on-plate-18-56a8b9625f9b58b7d0f49e73.jpg"
                  height=" 75px"
                  width="75px"
                  alt="Picture of grilled pork sandwich"
                />
                <figcaption>
                  <input
                    type="radio"
                    name="sandwich"
                    value="Grilled Pork"
                    v-model="picked_sandwich"
                  />Grilled Pork $9.50
                </figcaption>
              </figure>
            </td>
          </tr>
          <tr>
            <td>
              <label for="sandwichquantity">Quantity:</label>
              <input
                type="number"
                name="sandwichquantity"
                id="sandwichquantity"
                min="0"
                v-model="sandwich_quantity"
              />
            </td>
          </tr>
        </table>
      </table>
    </fieldset>
    <fieldset>
      <legend>
        <h2>Drink Choices</h2>
      </legend>
      <table>
        <tr>
          <td>
            <input
              type="radio"
              name="drink"
              value="Cola"
              v-model="picked_drink"
            />Cola
            <input
              type="radio"
              name="drink"
              value="Orange"
              v-model="picked_drink"
            />Orange
            <input
              type="radio"
              name="drink"
              value="Lemon"
              v-model="picked_drink"
            />Lemon
            <input
              type="radio"
              name="drink"
              value="Rootbeer"
              v-model="picked_drink"
            />Root Beer
          </td>
        </tr>
        <tr>
          <td>
            <input
              type="radio"
              name="drinksize"
              value="Small"
              v-model="drink_size"
            />Small $1.25
            <input
              type="radio"
              name="drinksize"
              value="Medium"
              v-model="drink_size"
            />Medium $1.75
            <input
              type="radio"
              name="drinksize"
              value="Large"
              v-model="drink_size"
            />Large $2.00
          </td>
        </tr>
        <tr>
          <td>
            <label for="drinkquantity">Quantity:</label>
            <input
              type="number"
              name="drinkquantity"
              id="drinkquantity"
              min="0"
              v-model="drink_quantity"
            />
          </td>
        </tr>
      </table>
    </fieldset>
    <div class="spacing" style="text-align: center;">
      <button>Submit</button>
    </div>
  </form>
</template>

<script>
export default {
  data() {
    return {
      fullname: "",
      address: "",
      phone: "",
      picked_pizza: "",
      pizza_size: "",
      pizza_cost: "",
      pizza_quantity: "",
      picked_sandwich: "",
      sandwich_cost: "",
      sandwich_quantity: "",
      picked_drink: "",
      drink_size: "",
      drink_cost: "",
      drink_quantity: "",
      orderDetails: "",
    };
  },
  methods: {
    checkOrder() {
      //Check for pizza size
      if (this.pizza_size == "Small") {
        this.pizza_cost = 8.5;
      }
      if (this.pizza_size == "Medium") {
        this.pizza_cost = 11.5;
      }
      if (this.pizza_size == "Large") {
        this.pizza_cost = 14.0;
      }
      if (this.pizza_size == "Small") {
        this.pizza_cost = 16.5;
      }

      //Check type of sandwich
      if (this.picked_sandwich == "All Garden Vegetarian") {
        this.sandwich_cost = 7.5;
      }
      if (this.picked_sandwich == "Big Beef on a Bun") {
        this.sandwich_cost = 8.5;
      }
      if (
        this.picked_sandwich == "Mixed Grill" ||
        this.picked_sandwich == "Grilled Pork"
      ) {
        this.sandwich_cost = 9.5;
      }

      //Check size of drink
      if (this.drink_size == "Small") {
        this.drink_cost = 1.25;
      }
      if (this.drink_size == "Medium") {
        this.drink_cost = 1.75;
      }
      if (this.drink_size == "Large") {
        this.drink_cost = 2.0;
      }

      //Calculate Total Cost
      const totalCost =
        this.pizza_cost * this.pizza_quantity +
        this.sandwich_cost * this.sandwich_quantity +
        this.drink_cost * this.drink_quantity;

      //Popup box of order details
      window.alert(
        "Order Details: " +
          "\n" +
          "Fullname: " +
          this.fullname +
          "\n" +
          "Address: " +
          this.address +
          "\n" +
          "Phone: " +
          this.phone +
          "\n" +
          "Food: " +
          this.pizza_quantity +
          " " +
          this.pizza_size +
          " " +
          this.picked_pizza +
          "\n" +
          this.sandwich_quantity +
          " " +
          this.picked_sandwich +
          "\n" +
          this.drink_quantity +
          " " +
          this.drink_size +
          " " +
          this.picked_drink +
          "\n" +
          "Total Cost: " +
          totalCost.toFixed(2) +
          "$\n"
      );
    },
  },
};
</script>

<style scoped>
.spacing {
  padding: 50px;
}
</style>
