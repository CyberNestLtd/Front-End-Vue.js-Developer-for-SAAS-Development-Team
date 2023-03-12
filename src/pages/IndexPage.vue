<template>
  <q-page class="">
      <div class="q-pa-md">
        <div class="checkout-page">
          <div class="row q-col-gutter-lg main-row">
            <div class="col-md-6 col-sm-12 col-xs-12">
              <form>
                <q-card class="main-card">
                  <div class="desktop-title-info">
                    <h2>Checkout</h2>
                    <q-tabs
                      v-model="tab"
                      content-class="custom-tabs"
                      active-color="primary"
                      indicator-color="primary"
                    >
                      <q-tab name="information" ripple="false">
                        <span>1</span>
                        <q-label>Information</q-label>
                      </q-tab>
                      <q-tab name="payment" ripple="false">
                        <span>2</span>
                        <q-label>Payment</q-label>
                      </q-tab>
                    </q-tabs>
                  </div>
                  <!-- Lifetime Warranty -->
                  <q-card class="warranty-card custom-card-box q-mb-lg">
                    <q-card-section>
                      <div class="text-h6">Lifetime Warranty</div>
                      <p>Add a lifetime warranty &amp; enjoy peace of mind for life with your dream collections order for just $4.99</p>
                      <q-btn>Add-$4.99</q-btn>
                    </q-card-section>
                  </q-card>
                  <!-- Express Checkout -->
                  <q-card class="express-checkout custom-card-box bg-white with-shadow">
                    <q-card-section>
                      <div class="text-h6">Express Checkout</div>
                      <div class="button-group">
                        <q-btn class="shoppay-btn">
                          <img alt="Shoppay" src="~assets/shoppay.png">
                        </q-btn>
                        <q-btn class="paypal-btn">
                          <img alt="Paypal" src="~assets/paypal.png">
                        </q-btn>
                        <q-btn class="gpay-btn">
                          <img alt="Gpay" src="~assets/g-pay.png">
                        </q-btn>
                      </div>
                    </q-card-section>
                  </q-card>
                  <q-tab-panels v-model="tab">
                    <q-tab-panel name="information">
                      <!-- Contact information -->
                      <div class="contact-information custom-form">
                        <div class="text-h6 q-mb-lg text-weight-medium">Contact Information</div>
                        <div class="q-mb-lg">
                          <div class="label">Email</div>
                          <q-input outlined v-model="text" placeholder="Enter your email">
                              <template v-slot:prepend>
                                <div class="label-icon"><img src="~assets/icons/message.svg" /></div>
                              </template>
                          </q-input>
                        </div>
                        <div class="q-mb-lg">
                          <div class="label">Phone Number</div>
                          <q-input outlined v-model="text" mask="(###) ### - ###" placeholder="Enter your phone number">
                              <template v-slot:prepend>
                                <div class="label-icon"><img src="~assets/icons/phone.svg" /></div>
                              </template>
                          </q-input>
                        </div>
                      </div>
                      <!-- Shipping address -->
                      <div class="contact-information custom-form">
                        <div class="text-h6 q-mb-lg text-weight-medium">Shipping Address</div>
                        <div class="q-mb-lg">
                          <div class="label">Country of Origin</div>
                          <q-select outlined v-model="model" :options="options">
                              <template v-slot:prepend>
                                <div class="label-icon"><img src="~assets/icons/map.svg" /></div>
                              </template>
                            </q-select>
                        </div>
                        <div class="row custom-row">
                            <div class="col-md-6 col-sm-12 col-xs-12">
                              <div class="q-mb-lg q-pa-sm">
                                <div class="label">First Name</div>
                                <q-input outlined v-model="text"  placeholder="Enter your first name" :rules="[ val => val.length <= 3 || 'Please use maximum 3 characters']">
                                    <template v-slot:prepend>
                                      <div class="label-icon"><img src="~assets/icons/user.svg" /></div>
                                    </template>
                                </q-input>
                              </div>
                            </div>
                            <div class="col-md-6 col-sm-12 col-xs-12">
                              <div class="q-mb-lg q-pa-sm">
                                <div class="label">last Name</div>
                                <q-input outlined v-model="text" placeholder="Enter your last name">
                                    <template v-slot:prepend>
                                      <div class="label-icon"><img src="~assets/icons/user.svg" /></div>
                                    </template>
                                </q-input>
                              </div>
                            </div>
                        </div>
                        <div class="q-mb-lg">
                          <div class="label">Address</div>
                          <q-input outlined v-model="text" placeholder="Enter your address">
                              <template v-slot:prepend>
                                <div class="label-icon"><img src="~assets/icons/map-marker.svg" /></div>
                              </template>
                          </q-input>
                        </div>
                        <div class="row custom-row">
                          <div class="col-md-6 col-sm-12 col-xs-12">
                            <div class="q-mb-lg q-pa-sm">
                              <div class="label">Apartment <span>(optional)</span></div>
                              <q-input outlined v-model="text" placeholder="Enter your apartment">
                                  <template v-slot:prepend>
                                    <div class="label-icon"><img src="~assets/icons/building.svg" /></div>
                                  </template>
                              </q-input>
                            </div>
                          </div>
                          <div class="col-md-6 col-sm-12 col-xs-12">
                            <div class="q-mb-lg q-pa-sm">
                              <div class="label">Suit <span>(optional)</span></div>
                              <q-input outlined v-model="text" placeholder="Enter your suit">
                                  <template v-slot:prepend>
                                    <div class="label-icon"><img src="~assets/icons/building.svg" /></div>
                                  </template>
                              </q-input>
                            </div>
                          </div>
                          <div class="col-md-6 col-sm-12 col-xs-12">
                            <div class="q-mb-lg q-pa-sm">
                              <div class="label">Post Code</div>
                              <q-input outlined v-model="text" placeholder="Enter your post code">
                                  <template v-slot:prepend>
                                    <div class="label-icon"><img src="~assets/icons/plus-marker.svg" /></div>
                                  </template>
                              </q-input>
                            </div>
                          </div>
                          <div class="col-md-6 col-sm-12 col-xs-12">
                            <div class="q-mb-lg q-pa-sm">
                              <div class="label">City</div>
                              <q-select outlined v-model="model" :options="options">
                                <template v-slot:prepend>
                                  <div class="label-icon"><img src="~assets/icons/map-marker.svg" /></div>
                                </template>
                              </q-select>
                            </div>
                          </div>
                        </div>
                        <div class="continue-to-payment">
                          <q-tabs
                            v-model="tab"
                          >
                            <q-tab name="payment">
                              <button>
                                <div class="q-pr-sm">Continue to Payment</div>
                                <q-icon left size="1.2em" name="east" />
                              </button>
                            </q-tab>
                          </q-tabs>
                        </div>
                      </div>
                    </q-tab-panel>
                    <q-tab-panel name="payment">
                      <div class="payment-section q-mt-md">
                        <div class="text-h5 q-mb-lg text-weight-medium">Payment</div>
                        <div class="payment-option">
                            <q-btn>
                              <div class="label-icon"><img src="~assets/icons/card-active.svg" /></div>
                              <div class="q-pr-sm">Credit Card</div>
                            </q-btn>
                            <q-btn class="paypal-btn">
                              <div class="label-icon"><img src="~assets/icons/paypal-icon.svg" /></div>
                              <div class="q-pr-sm">Paypal</div>
                            </q-btn>
                        </div>
                        <div class="payment-form custom-form">
                          <div class="q-mb-lg">
                            <div class="label">Credit Card Number</div>
                            <q-input outlined v-model="text" mask="####  ####  ####  ####" placeholder="2548 9841 2570 ****">
                                <template v-slot:prepend>
                                  <div class="label-icon"><img src="~assets/icons/card-grey.svg" /></div>
                                </template>
                            </q-input>
                          </div>
                          <div class="q-mb-lg">
                            <div class="label">Name on card</div>
                            <q-input outlined v-model="text" placeholder="Enter name on card">
                                <template v-slot:prepend>
                                  <div class="label-icon"><img src="~assets/icons/card-grey.svg" /></div>
                                </template>
                            </q-input>
                          </div>
                          <div class="row custom-row">
                            <div class="col-md-6 col-sm-12 col-xs-12">
                              <div class="q-mb-lg q-pa-sm">
                                <div class="label">Expiry Date</div>
                                <q-input outlined v-model="text" placeholder="MM/YY">
                                    <template v-slot:append>
                                      <div class="label-icon"><img src="~assets/icons/calender.svg" /></div>
                                    </template>
                                </q-input>
                              </div>
                            </div>
                            <div class="col-md-6 col-sm-12 col-xs-12">
                              <div class="q-mb-lg q-pa-sm">
                                <div class="label">Security</div>
                                <q-input outlined v-model="text" placeholder="CVV">
                                    <template v-slot:prepend>
                                      <div class="label-icon"><img src="~assets/icons/message.svg" /></div>
                                    </template>
                                </q-input>
                              </div>
                            </div>
                          </div>
                          <div class="agreement-checkbox q-mb-xl">
                            <q-checkbox v-model="left">
                              <div class="text-body">By checking this box, I acknowledge that I have read and agree to the <strong>Terms of Service</strong>, and <strong>Monthly Billing Terms</strong> of this website and want to opt-in for the monthly billed Dream Collection Club®</div>
                            </q-checkbox>
                          </div>
                          <!-- Billing address -->
                          <div class="billing-address q-mb-lg">
                            <div class="text-h5 q-mb-sm text-weight-medium">Billing Address</div>
                            <p>Specify the address for your payment option</p>
                            <q-radio v-model="billing_address_type" val="same-shipping" label="Same as shipping address" />
                            <q-radio v-model="billing_address_type" val="different-shipping" label="Use a different billing address" />
                          </div>
                          <div v-if='billing_address_type === "different-shipping"'>
                            <div class="q-mb-lg">
                              <div class="label">Country of Origin</div>
                                <q-select outlined v-model="model" :options="options">
                                    <template v-slot:prepend>
                                      <div class="label-icon"><img src="~assets/icons/map.svg" /></div>
                                    </template>
                                  </q-select>
                              </div>
                              <div class="row custom-row">
                                  <div class="col-md-6 col-sm-12 col-xs-12">
                                    <div class="q-mb-lg q-pa-sm">
                                      <div class="label">First Name</div>
                                      <q-input outlined v-model="text" placeholder="Enter your first name" :rules="[ val => val.length <= 3 || 'Please use maximum 3 characters']">
                                          <template v-slot:prepend>
                                            <div class="label-icon"><img src="~assets/icons/user.svg" /></div>
                                          </template>
                                      </q-input>
                                    </div>
                                  </div>
                                  <div class="col-md-6 col-sm-12 col-xs-12">
                                    <div class="q-mb-lg q-pa-sm">
                                      <div class="label">last Name</div>
                                      <q-input outlined v-model="text" placeholder="Enter your last name">
                                          <template v-slot:prepend>
                                            <div class="label-icon"><img src="~assets/icons/user.svg" /></div>
                                          </template>
                                      </q-input>
                                    </div>
                                  </div>
                              </div>
                              <div class="q-mb-lg">
                                <div class="label">Address</div>
                                <q-input outlined v-model="text" placeholder="Enter your address">
                                    <template v-slot:prepend>
                                      <div class="label-icon"><img src="~assets/icons/map-marker.svg" /></div>
                                    </template>
                                </q-input>
                              </div>
                              <div class="row custom-row">
                                <div class="col-md-6 col-sm-12 col-xs-12">
                                  <div class="q-mb-lg q-pa-sm">
                                    <div class="label">Apartment <span>(optional)</span></div>
                                    <q-input outlined v-model="text" placeholder="Enter your apartment">
                                        <template v-slot:prepend>
                                          <div class="label-icon"><img src="~assets/icons/building.svg" /></div>
                                        </template>
                                    </q-input>
                                  </div>
                                </div>
                                <div class="col-md-6 col-sm-12 col-xs-12">
                                  <div class="q-mb-lg q-pa-sm">
                                    <div class="label">Suit <span>(optional)</span></div>
                                    <q-input outlined v-model="text" placeholder="Enter your suit">
                                        <template v-slot:prepend>
                                          <div class="label-icon"><img src="~assets/icons/building.svg" /></div>
                                        </template>
                                    </q-input>
                                  </div>
                                </div>
                                <div class="col-md-6 col-sm-12 col-xs-12">
                                  <div class="q-mb-lg q-pa-sm">
                                    <div class="label">Post Code</div>
                                    <q-input outlined v-model="text" placeholder="Enter your post code">
                                        <template v-slot:prepend>
                                          <div class="label-icon"><img src="~assets/icons/plus-marker.svg" /></div>
                                        </template>
                                    </q-input>
                                  </div>
                                </div>
                                <div class="col-md-6 col-sm-12 col-xs-12">
                                  <div class="q-mb-lg q-pa-sm">
                                    <div class="label">City</div>
                                    <q-select outlined v-model="model" :options="options">
                                      <template v-slot:prepend>
                                        <div class="label-icon"><img src="~assets/icons/map-marker.svg" /></div>
                                      </template>
                                    </q-select>
                                  </div>
                                </div>
                              </div>
                          </div>
                          <div class="continue-to-payment q-mt-md">
                            <q-btn>
                              <div class="q-pr-sm">Complete Purchase</div>
                              <q-icon left size="1.2em" name="east" />
                            </q-btn>
                          </div>
                        </div>
                      </div>
                    </q-tab-panel>
                  </q-tab-panels>
                </q-card>
              </form>
            </div>
            <div class="col-md-6 col-sm-12 col-xs-12">
              <div class="mobile-title-info">
                <h2>Checkout</h2>
                <q-tabs
                  v-model="tab"
                  content-class="custom-tabs"
                  active-color="primary"
                  indicator-color="primary"
                >
                  <q-tab name="information" ripple="false">
                    <span>1</span>
                    <q-label>Information</q-label>
                  </q-tab>
                  <q-tab name="payment" ripple="false">
                    <span>2</span>
                    <q-label>Payment</q-label>
                  </q-tab>
                </q-tabs>
              </div>
              <div class="order-summary-box">
                <q-expansion-item>
                  <template v-slot:header>
                    <q-item-section class="icon-box">
                      <img src="~assets/icons/shopping.svg" alt="">
                    </q-item-section>
                    <q-item-section>
                      Show Order Summary
                    </q-item-section>
                    <q-item-section side>
                      <div class="total-price">€138.00</div>
                    </q-item-section>
                  </template>
                  <q-card>
                    <div class="summary-list custom-card-box q-mb-lg">
                      <q-card-section>
                        <div class="text-h6">Order Summary <span>#26450</span></div>
                        <div class="q-mb-xl">
                          <OrderSummaryVue
                            v-for="link in essentialLinks"
                            :key="link.title"
                            v-bind="link"
                          />
                        </div>
                        <div class="q-mb-xl">
                          <DiscountBoxVue />
                        </div>
                        <div class="cart-total-price">
                            <div class="flex justify-between">
                                <div>Subtotal:</div>
                                <div>$362.79</div>
                            </diV>
                            <div class="flex justify-between">
                                <div>Shipping:</div>
                                <div>Free</div>
                            </diV>
                            <div class="flex justify-between total-price">
                                <div>Total</div>
                                <div><strong>$362.70</strong></div>
                            </diV>
                        </div>
                      </q-card-section>
                    </div>
                  </q-card>
                </q-expansion-item>
                <div class="other-information custom-card-box with-shadow bg-white q-mb-lg">
                  <q-card-section>
                    <div class="flex no-wrap items-center other-info-list">
                      <div class="icon">
                        <img src="~assets/cashback.svg" alt="">
                      </div>
                      <div class="text-details">
                        <p>30 days satisfaction <strong>Gaurantee</strong> with <strong>money back</strong></p>
                      </div>
                    </div>
                    <div class="flex no-wrap items-center other-info-list">
                      <div class="icon">
                        <img src="~assets/truck.svg" alt="">
                      </div>
                      <div class="text-details">
                        <p>Over <strong>38,957</strong> successfully <strong>shipped orders</strong></p>
                      </div>
                    </div>
                  </q-card-section>
                </div>
                <div class="extra-features custom-card-box with-shadow bg-white">
                  <q-card-section>
                    <div class="text-h6">The ultimate jewellery club</div>
                  <p>Ornare rhoncus nunc ut felis. Faucibus dolor at ultrices tincidunt. Pulvinar sed justo et viverra pellentesque.</p>
                  <q-item dense>
                    <q-item-section avatar>
                      <q-icon color="primary" name="done" />
                    </q-item-section>
                    <q-item-section>Extra 10$ off!</q-item-section>
                  </q-item>
                  <q-item dense>
                    <q-item-section avatar>
                      <q-icon color="primary" name="done" />
                    </q-item-section>
                    <q-item-section>Free shipping on marked club items!</q-item-section>
                  </q-item>
                  <q-item dense>
                    <q-item-section avatar>
                      <q-icon color="primary" name="done" />
                    </q-item-section>
                    <q-item-section>Free returns on marked club items!</q-item-section>
                  </q-item>
                  </q-card-section>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
  </q-page>
</template>
<script>
import { defineComponent, ref } from 'vue'
import DiscountBoxVue from '../components/DiscountBox.vue'
import OrderSummaryVue from '../components/OrderSummary.vue'
import imageOne from '../assets/image1.png'
import imageTwo from '../assets/image2.png'
import imageThree from '../assets/image3.png'

const linksList = [
  {
    title: 'Nike sneakers',
    qty: '1',
    image: imageOne,
    price: '$120.90'
  },
  {
    title: 'Nike sneakers',
    qty: '1',
    image: imageTwo,
    price: '$120.90'
  },
  {
    title: 'Nike sneakers',
    qty: '1',
    image: imageThree,
    price: '$120.90'
  }
]
export default defineComponent({
  name: 'IndexPage',

  components: {
    OrderSummaryVue,
    DiscountBoxVue
  },
  data () {
    return {
      essentialLinks: linksList
    }
  },
  setup () {
    return {
      tab: ref('information'),
      model: ref(null),
      billing_address_type: ref('same-shipping'),
      left: ref(true),
      options: [
        'Google', 'Facebook', 'Twitter', 'Apple', 'Oracle'
      ]
    }
  }
})
</script>
