// Create armature
var armature = Dynamo.Geometry.Armature.Create(
    numberOfPoints: 10,
    radius: 5,
    height: 10,
    startAngle: 0,
    endAngle: 180
);

// Transform armature
var transform = armature.Transform(
    translation: [0, 10, 0],
    rotation: [0, 0, 45]
);

// Create geometry from armature
var geometry = Dynamo.Geometry.ByGeometry.Create(
    geometry: transform,
    type: Dynamo.Geometry.GeometryType.BREP
);

// Create element from geometry
var element = Dynamo.Elements.Element.Create(
    geometry: geometry,
    type: Dynamo.Elements.ElementType.FAMILY_INSTANCE
);
