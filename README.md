# Imagga::Categorization

This gem is a simple wrapper around Imagga's categorization API.

## Installation

Add this line to your application's Gemfile:

    gem 'imagga-categorization'

And then execute:

    $ bundle

Or install it yourself as:

    $ gem install imagga-categorization

## Usage

**Create a client**

``` ruby
client = Imagga::Categorization::Client.new app_key: YOUR_API_KEY
```

**Consume an endpoint**

The gem currently supports 3 endpoints:
- `/draft/classify/{classifier_id}`
- `/draft/classify/result/{ticket_id}`
- `/draft/tasks/{task_id}`

Imagga's full api documentation [can be found here](http://docs.imagga.apiary.io/#classification). It lists the possible parameters for each endpoint.

**Classify**

```ruby
parameters = {
  "async": "1",
  "urls": "https://fbcdn-sphotos-h-a.akamaihd.net/hphotos-ak-prn2/969321_526818917353598_661738580_n.jpg, http://example.com/image2.jpg"
}
response = client.classify(YOUR_CLASSIFIER_ID, parameters)
```

**Classify result**

```ruby
response = client.classify(ticket_id)
```

**Task result**

```ruby
response = client.classify(task_id)
```

## Contributing

1. Fork it
2. Create your feature branch (`git checkout -b my-new-feature`)
3. Commit your changes (`git commit -am 'Add some feature'`)
4. Push to the branch (`git push origin my-new-feature`)
5. Create new Pull Request
