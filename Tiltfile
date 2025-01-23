# Build
gradlew = "gradlew"
expected_ref = "%EXPECTED_REF%"
custom_build(
     ref = 'catalog-service',
     command = gradlew + ' bootBuildImage --imageName ' + expected_ref,
     deps = ['build.gradle', 'src']
)

# Deploy
k8s_yaml(['k8s/deployment.yml', 'k8s/service.yml'])

# Manage
k8s_resource('catalog-service', port_forwards=['9001'])