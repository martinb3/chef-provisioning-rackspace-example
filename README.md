# chef-provisioning-rackspace-example

Feel free to browse right to the [create](recipes/create.rb) and [destroy](recipes/destroy.rb) examples.

## Configuring

You must configure some credentials and region in a `knife.rb` file like so:
```
driver 'fog:Rackspace'
driver_options :compute_options => {
  :rackspace_username => 'my_rackspace_user',
  :rackspace_api_key  => 'api_key_for_user',
  :rackspace_region => 'dfw' # could be 'org', 'iad', 'hkg', etc
}
```

NB: If you run into SSH key trouble, [see this issue](https://github.com/chef/chef-provisioning-fog/issues/130) for some background of the chef-provisioning-fog driver and the fog library's different ways of bootstraping a server at Rackspace.

## How to run

This example can be run using the following commands:
```
bundle exec chef-client -z recipes/create.rb
bundle exec chef-client -z recipes/destroy.rb
```
